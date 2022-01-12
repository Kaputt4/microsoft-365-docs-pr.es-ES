---
title: Recomendaciones de Microsoft para EOP y Defender para la configuración Office 365 seguridad
keywords: Office 365 de seguridad, Marco de directivas de remitente, Informes y conformidad de mensajes basados en dominio, DomainKeys Identified Mail, pasos, cómo funciona, líneas base de seguridad, líneas base para EOP, líneas base para Defender para Office 365 , configurar Defender para Office 365 , configurar EOP, configurar Defender para Office 365 , configurar EOP, configuración de seguridad
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
description: ¿Cuáles son los procedimientos recomendados para Exchange Online Protection (EOP) y Defender para Office 365 de seguridad? ¿Cuáles son las recomendaciones actuales para la protección estándar? ¿Qué se debe usar si quiere ser más estricto? ¿Y qué extras obtiene si también usa Defender para Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2b894344362556200362d486853d56a2aed00b6
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61943117"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configuración recomendada de seguridad para EOP y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** es el núcleo de seguridad de las suscripciones de Microsoft 365 y ayuda a evitar que los correos electrónicos malintencionados lleguen a las bandejas de entrada de los empleados. Sin embargo, con ataques nuevos y más sofisticados que surgen cada día, a menudo se requieren protecciones mejoradas. **Microsoft Defender para Office 365** Plan 1 o Plan 2 contienen características adicionales que dan a los administradores más capas de seguridad, control e investigación.

Aunque habilitamos a los administradores de seguridad para personalizar su configuración de seguridad, hay dos niveles de seguridad en EOP y Microsoft Defender para Office 365 que recomendamos: **Standard** y **Strict**. Aunque los entornos y las necesidades de los clientes son diferentes, estos niveles de filtrado ayudarán a evitar que el correo no deseado llegue a la Bandeja de entrada de los empleados en la mayoría de las situaciones.

Para aplicar automáticamente la configuración Estándar o Estricta a los usuarios, consulte [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

En este artículo se describe la configuración predeterminada y también la configuración estándar y estricta recomendada para ayudar a proteger a los usuarios. Las tablas contienen la configuración del portal Microsoft 365 Defender y PowerShell (Exchange Online PowerShell o powershell independiente Exchange Online Protection powershell para organizaciones sin Exchange Online buzones de correo).

> [!TIP]
> No puede cambiar la configuración estándar y estricta recomendada en el portal Microsoft 365 Defender web. Para cambiar los valores recomendados, como **Permitir que los usuarios** protejan, debe usar Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
>
> El Office 365 advanced threat protection recommended configuration analyzer (ORCA) para PowerShell puede ayudarle (administradores) a encontrar los valores actuales de esta configuración. En concreto, el cmdlet **Get-ORCAReport** genera una evaluación de la configuración contra correo no deseado, contra suplantación de identidad (phishing) y otras opciones de higiene de mensajes. Puede descargar el módulo ORCA en <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo no deseado, antimalware y anti phishing en EOP

El correo no deseado, el antimalware y la suplantación de identidad (phishing) son características de EOP que pueden configurar los administradores. Se recomiendan las siguientes configuraciones estándar o estrictas.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de directiva contra correo no deseado de EOP

Para crear y configurar directivas contra correo no deseado, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbral de correo electrónico masivo & de correo no deseado**|||||
|**Umbral de correo electrónico masivo** <p> _BulkThreshold_|7 |6 |4|Para obtener más información, [vea Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|Esta configuración solo está disponible en PowerShell.|
|**Aumentar la configuración de puntuación de correo** no deseado|Desactivado|Desactivado|Desactivado|Todas estas opciones de configuración forman parte del filtro de correo no deseado avanzado (ASF). Para obtener más información, vea la sección [Configuración de ASF en directivas contra correo](#asf-settings-in-anti-spam-policies) no deseado en este artículo.|
|**Marcar como configuración de correo** no deseado|Desactivado|Desactivado|Desactivado|La mayoría de estas opciones de configuración forman parte de ASF. Para obtener más información, vea la sección [Configuración de ASF en directivas contra correo](#asf-settings-in-anti-spam-policies) no deseado en este artículo.|
|**Contiene idiomas específicos** <p> _EnableLanguageBlockList_ <p> _LanguageBlockList_|**Desactivado** <p> `$false` <p> En blanco|**Desactivado** <p> `$false` <p> En blanco|**Desactivado** <p> `$false` <p> En blanco|No tenemos ninguna recomendación específica para esta configuración. Puede bloquear mensajes en idiomas específicos en función de sus necesidades empresariales.|
|**Desde estos países** <p> _EnableRegionBlockList_ <p> _RegionBlockList_|**Desactivado** <p> `$false` <p> En blanco|**Desactivado** <p> `$false` <p> En blanco|**Desactivado** <p> `$false` <p> En blanco|No tenemos ninguna recomendación específica para esta configuración. Puede bloquear mensajes de países específicos en función de sus necesidades empresariales.|
|**Modo de prueba** (_TestModeAction_)|**Ninguna**|**Ninguna**|**Ninguna**|Esta configuración forma parte de ASF. Para obtener más información, vea la sección [Configuración de ASF en directivas contra correo](#asf-settings-in-anti-spam-policies) no deseado en este artículo.|
|**Acciones**||||Donde quiera que seleccione **Mensaje de cuarentena,** hay disponible un cuadro Seleccionar directiva **de** cuarentena. Las directivas de cuarentena definen lo que los usuarios pueden hacer en los mensajes en cuarentena. <p> Al crear una nueva directiva contra correo no deseado, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena por ese veredicto en particular (AdminOnlyAccessPolicy para **phishing** de elevada confianza ; DefaultFullAccessPolicy para todo lo demás). <p> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen capacidades más restrictivas o menos restrictivas para los usuarios. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).|
|**Acción de detección de correo** no deseado <p> _SpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección de correo no deseado** de elevada confianza <p> _HighConfidenceSpamAction_|**Colocar el mensaje en cuarentena** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección** de phishing <p> _PhishSpamAction_|**Colocar el mensaje en cuarentena** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de detección de phishing de elevada** confianza <p> _HighConfidencePhishAction_|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Acción de** detección masiva <p> _BulkSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <p> `MoveToJmf`|**Colocar el mensaje en cuarentena** <p> `Quarantine`||
|**Conservar el correo no deseado en cuarentena durante estos días** <p> _QuarantineRetentionPeriod_|15 días<sup>\*</sup>|30 días|30 días|<sup>\*</sup> El valor predeterminado es 15 días en la directiva contra correo no deseado predeterminada y en las nuevas directivas contra correo no deseado que cree en PowerShell. El valor predeterminado es 30 días en las nuevas directivas contra correo no deseado que cree en el portal de Microsoft 365 Defender. <p> Este valor también afecta a los mensajes que están en cuarentena mediante directivas contra suplantación de identidad. Para obtener más información, vea [Quarantined email messages in EOP](quarantine-email-messages.md).|
|**Habilitar sugerencias de seguridad contra correo no deseado** <p> _InlineSafetyTipsEnabled_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|Habilitar la purga automática de hora cero (ZAP) para mensajes de suplantación de identidad <p> _PhishZapEnabled_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|Habilitar ZAP para mensajes de correo no deseado <p> _SpamZapEnabled_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Permitir & de bloques**|||||
|Remitentes permitidos <p> _AllowedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente permitidos <p> _AllowedSenderDomains_|Ninguno|Ninguno|Ninguno|Agregar dominios a la lista de remitentes permitidos es una idea muy mala. Los atacantes podrían enviarle un correo electrónico que, de lo contrario, se filtraría. <p> Use [](learn-about-spoof-intelligence.md) la información de inteligencia de suplantación de identidad y la lista de permitidos [o](tenant-allow-block-list.md) bloqueados de inquilinos para revisar todos los remitentes que suplanten direcciones de correo electrónico de remitente en los dominios de correo electrónico de su organización o suplanten direcciones de correo electrónico de remitente en dominios externos.|
|Remitentes bloqueados <p> _BlockedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente bloqueados <p> _BlockedSenderDomains_|Ninguno|Ninguno|Ninguno||
|

#### <a name="asf-settings-in-anti-spam-policies"></a>Configuración de ASF en directivas contra correo no deseado

En la tabla de esta sección se describe la configuración del filtro de correo no deseado avanzado (ASF) que están disponibles en las directivas contra correo no deseado. Todas estas opciones de configuración están **desactivadas** para **los niveles Estándar** **y** Estricto. Para obtener más información acerca de la configuración de ASF, vea [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).

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
|**Modo de prueba** (_TestModeAction_)|Para las opciones de ASF compatibles con **Test** como acción, puede configurar la acción del modo de prueba en **None**, **Add default X-Header text** o Send **CCO message** ( , , , or `None` `AddXHeader` `BccMessage` ). Para obtener más información, vea [Habilitar, deshabilitar o probar la configuración de ASF](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings).|
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
|**Enviar una copia de mensajes salientes que superen estos límites a estos usuarios y grupos** <p> _BccSuspiciousOutboundMail_ <p> _BccSuspiciousOutboundAdditionalRecipients_|No seleccionada <p> `$false` <p> En blanco|No seleccionada <p> `$false` <p> En blanco|No seleccionada <p> `$false` <p> En blanco|No tenemos ninguna recomendación específica para esta configuración. <p> Esta configuración solo funciona en la directiva de correo no deseado saliente predeterminada. No funciona en las directivas de correo no deseado saliente personalizadas que cree.|
|**Notificar a estos usuarios y grupos si un remitente está bloqueado debido al envío de correo no deseado saliente** <p> _NotifyOutboundSpam_ <p> _NotifyOutboundSpamRecipients_|No seleccionada <p> `$false` <p> En blanco|No seleccionada <p> `$false` <p> En blanco|No seleccionada <p> `$false` <p> En blanco|La [directiva](../../compliance/alert-policies.md) de  alerta predeterminada denominada Usuario restringido para enviar correo electrónico ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**Administradores** globales ) cuando los usuarios se bloquean debido a que superan los límites de la directiva. **Se recomienda encarecidamente que use la** directiva de alertas en lugar de esta configuración en la directiva de correo no deseado saliente para notificar a los administradores y otros usuarios . Para obtener instrucciones, consulte [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).|
|

### <a name="eop-anti-malware-policy-settings"></a>Configuración de directiva antimalware de EOP

Para crear y configurar directivas antimalware, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Configuración de protección**|||||
|**Habilitar el filtro de datos adjuntos común** <p> _EnableFileFilter_|No seleccionada <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Esta configuración pone en cuarentena los mensajes que contienen datos adjuntos ejecutables según el tipo de archivo, independientemente del contenido de los datos adjuntos.|
|**Habilitar la purga automática de hora cero para malware** <p> _ZapEnabled_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Directiva de cuarentena**|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|Al crear una nueva directiva antimalware, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena como malware (AdminOnlyAccessPolicy). <p> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen más funcionalidades para los usuarios. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).|
|**Notificaciones de destinatarios**|||||
|**Notificar a los destinatarios cuando los mensajes se ponen en cuarentena como malware** <p> _Action_|No seleccionada <p> _DeleteMessage_|No seleccionada <p> _DeleteMessage_|No seleccionada <p> _DeleteMessage_|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pone en cuarentena y solo puede publicarlo un administrador.|
|**Notificaciones de remitente**|||||
|**Notificar a los remitentes internos cuando los mensajes se ponen en cuarentena como malware** <p> _EnableInternalSenderNotifications_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`||
|**Notificar a remitentes externos cuando los mensajes se ponen en cuarentena como malware** <p> _EnableExternalSenderNotifications_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`||
|**Notificaciones de administrador**|||||
|**Notificar a un administrador sobre los mensajes no entregados de remitentes internos** <p> _EnableInternalSenderAdminNotifications_ <p> _InternalSenderAdminAddress_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No tenemos ninguna recomendación específica para esta configuración.|
|**Notificar a un administrador sobre los mensajes no entregados de remitentes externos** <p> _EnableExternalSenderAdminNotifications_ <p> _ExternalSenderAdminAddress_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No tenemos ninguna recomendación específica para esta configuración.|
|**Personalizar notificaciones**||||No tenemos recomendaciones específicas para esta configuración.|
|**Usar texto de notificación personalizado** <p> _CustomNotifications_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`||
|**Nombre De** <p> _CustomFromName_|En blanco <p> `$null`|En blanco <p> `$null`|En blanco <p> `$null`||
|**Dirección de origen** <p> _CustomFromAddress_|En blanco <p> `$null`|En blanco <p> `$null`|En blanco <p> `$null`||
|**Personalizar notificaciones para mensajes de remitentes internos**||||Esta configuración solo se usa si se selecciona Notificar a **remitentes** internos cuando los mensajes se ponen en cuarentena como malware o notificar a un administrador sobre los mensajes no entregados de **remitentes** internos.|
|**Asunto** <p> _CustomInternalSubject_|En blanco <p> `$null`|En blanco <p> `$null`|En blanco <p> `$null`||
|**Message** <p> _CustomInternalBody_|En blanco <p> `$null`|En blanco <p> `$null`|En blanco <p> `$null`||
|**Personalizar notificaciones para mensajes de remitentes externos**||||Esta configuración solo se usa si se selecciona Notificar a **remitentes externos** cuando los mensajes se ponen en cuarentena como malware o notificar a un administrador sobre los mensajes no entregados de **remitentes externos.**|
|**Asunto** <p> _CustomExternalSubject_|En blanco <p> `$null`|En blanco <p> `$null`|En blanco <p> `$null`||
|**Message** <p> _CustomExternalBody_|En blanco <p> `$null`|En blanco <p> `$null`|En blanco <p> `$null`||
|

### <a name="eop-anti-phishing-policy-settings"></a>Configuración de directiva contra suplantación de identidad de EOP

Para obtener más información acerca de esta configuración, vea [Spoof settings](set-up-anti-phishing-policies.md#spoof-settings). Para configurar estas opciones, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección contra & phishing**|||||
|**Habilitar la inteligencia de suplantación** <p> _EnableSpoofIntelligence_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Acciones**|||||
|**Si el mensaje se detecta como suplantación** <p> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`|Esta configuración se aplica a remitentes suplantados que se [](learn-about-spoof-intelligence.md) bloquearon automáticamente, como se muestra en la información de inteligencia de suplantación de identidad o bloqueados manualmente en la lista de inquilinos permitidos [o bloqueados.](tenant-allow-block-list.md) <p> Si selecciona **Poner** en  cuarentena el mensaje, hay disponible un cuadro Aplicar directiva de cuarentena para seleccionar la directiva de cuarentena que define lo que los usuarios pueden hacer a los mensajes que se ponen en cuarentena como suplantación. Al crear una nueva directiva anti phishing, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena como suplantación de identidad (DefaultFullAccessPolicy). <p> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen capacidades más restrictivas o menos restrictivas para los usuarios. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).|
|**Mostrar el primer contacto consejo de seguridad** <p> _EnableFirstContactSafetyTips_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`|Para obtener más información, vea [First contact consejo de seguridad](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Mostrar (?) para remitentes no autenticados para suplantación de identidad** <p> _EnableUnauthenticatedSender_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|**Mostrar etiqueta "via"** <p> _EnableViaTag_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la **dirección MAIL FROM.** <p> Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender para la Office 365 seguridad

Las ventajas de seguridad adicionales vienen con una suscripción de Microsoft Defender para Office 365 suscripción. Para obtener las últimas noticias e información, puede ver [Novedades de Defender para Office 365](whats-new-in-defender-for-office-365.md).

> [!IMPORTANT]
>
> - La directiva contra suplantación de identidad predeterminada [](set-up-anti-phishing-policies.md#spoof-settings) en Microsoft Defender para Office 365 proporciona protección contra suplantación de identidad e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras [características](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) de protección de suplantación disponibles y la configuración avanzada [no](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) están configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva contra suplantación de identidad predeterminada o cree directivas adicionales contra la suplantación de identidad.
>
> - Aunque no hay ninguna directiva de datos adjuntos de Caja fuerte  predeterminada o una directiva de vínculos de Caja fuerte, la directiva de seguridad predefinida de protección integrada proporciona protección de datos adjuntos de Caja fuerte y protección de vínculos Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas de datos adjuntos de Caja fuerte personalizadas o Caja fuerte de vínculos). Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).
>
> - [Caja fuerte datos adjuntos para SharePoint, OneDrive y](mdo-for-spo-odb-and-teams.md) Microsoft Teams protección y protección Caja fuerte [Documentos](safe-docs.md) no tienen dependencias en las directivas Caja fuerte vínculos.

Si la suscripción incluye Microsoft Defender para Office 365 o si has comprado Defender para Office 365 como complemento, establece las siguientes configuraciones estándar o estrictas.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directiva contra suplantación de identidad en Microsoft Defender para Office 365

Los clientes de EOP obtienen la protección contra suplantación de identidad básica como se describió anteriormente, pero Defender para Office 365 incluye más características y control para ayudar a prevenir, detectar y corregir los ataques. Para crear y configurar estas directivas, vea [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración avanzada en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, consulte [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar esta configuración, vea [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbral de correo electrónico de suplantación de identidad** <p> _PhishThresholdLevel_|**1- Estándar** <p> `1`|**2 : agresivo** <p> `2`|**3: más agresivo** <p> `3`||
|

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, vea Configuración de suplantación en directivas contra suplantación en [Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar estas opciones, vea [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección contra & phishing**|||||
|**Permitir a los usuarios proteger** (protección de usuario suplantada) <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|No seleccionada <p> `$false` <p> ninguno|Seleccionado <p> `$true` <p> \<list of users\>|Seleccionado <p> `$true` <p> \<list of users\>|Se recomienda agregar usuarios (remitentes de mensajes) en roles clave. Internamente, los remitentes protegidos pueden ser su director general, director financiero y otros líderes sénior. Externamente, los remitentes protegidos podrían incluir miembros del consejo o su junta directiva. Las directivas de seguridad preestablecidas no se pueden modificar; deben deshabilitarse si desea agregar usuarios en roles clave como se sugiere.|
|**Habilitar dominios para proteger** (protección de dominio suplantada)|No seleccionada|Seleccionado|Seleccionado||
|**Incluir dominios de mi propiedad** <p> _EnableOrganizationDomainsProtection_|Desactivado <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Incluir dominios personalizados** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Desactivado <p> `$false` <p> ninguno|Seleccionado <p> `$true` <p> \<list of domains\>|Seleccionado <p> `$true` <p> \<list of domains\>|Se recomienda agregar dominios (dominios de remitente) que no posee, pero con los que interactúa con frecuencia.|
|**Agregar dominios y remitentes de confianza** <p> _ExcludedSenders_ <p> _ExcludedDomains_|Ninguno|Ninguno|Ninguno|Según la organización, se recomienda agregar remitentes o dominios que se identifiquen incorrectamente como intentos de suplantación.|
|**Habilitar la inteligencia de buzones** <p> _EnableMailboxIntelligence_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Habilitar la inteligencia para la protección de suplantación** <p> _EnableMailboxIntelligenceProtection_|Desactivado <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Esta configuración permite la acción especificada para las detecciones de suplantación por inteligencia de buzones.|
|**Acciones**||||Siempre que seleccione **Poner en cuarentena el mensaje,** hay disponible un cuadro Seleccionar directiva **de** cuarentena. Las directivas de cuarentena definen lo que los usuarios pueden hacer en los mensajes en cuarentena. <p> Al crear una nueva directiva anti phishing, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena por ese veredicto (DefaultFullAccessPolicy para todos los tipos de detección de suplantación). <p> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen capacidades menos restrictivas o más restrictivas para los usuarios. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).|
|**Si el mensaje se detecta como un usuario suplantado** <p> _TargetedUserProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Poner en cuarentena el mensaje** <p> `Quarantine`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|**Si el mensaje se detecta como un dominio suplantado** <p> _TargetedDomainProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Poner en cuarentena el mensaje** <p> `Quarantine`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|**Si la inteligencia de buzones detecta y suplanta al usuario** <p> _MailboxIntelligenceProtectionAction_|**No aplicar ninguna acción** <p> `NoAction`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`||
|**Mostrar la suplantación de usuario consejo de seguridad** <p> _EnableSimilarUsersSafetyTips_|Desactivado <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Mostrar la suplantación de dominio consejo de seguridad** <p> _EnableSimilarDomainsSafetyTips_|Desactivado <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Mostrar caracteres inusuales de suplantación de usuario consejo de seguridad** <p> _EnableUnusualCharactersSafetyTips_|Desactivado <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directiva contra suplantación de identidad de EOP en Microsoft Defender para Office 365

Estas son las mismas opciones que están disponibles en la configuración [de directiva contra correo no deseado en EOP](#eop-anti-spam-policy-settings).

La configuración de suplantación de  dominio está interrelacionado, pero la configuración Mostrar primer contacto consejo de seguridad no depende de la configuración de suplantación.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección contra & phishing**|||||
|**Habilitar la inteligencia de suplantación** <p> _EnableSpoofIntelligence_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Acciones**|||||
|**Si el mensaje se detecta como suplantación** <p> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <p> `MoveToJmf`|**Poner en cuarentena el mensaje** <p> `Quarantine`|Esta configuración se aplica a remitentes suplantados que se [](learn-about-spoof-intelligence.md) bloquearon automáticamente, como se muestra en la información de inteligencia de suplantación de identidad o bloqueados manualmente en la lista de inquilinos permitidos [o bloqueados.](tenant-allow-block-list.md) <p> Si selecciona Poner en  cuarentena **el** mensaje, hay disponible un cuadro Aplicar directiva de cuarentena para seleccionar la directiva de cuarentena que define lo que los usuarios pueden hacer a los mensajes en cuarentena. Al crear una nueva directiva anti phishing, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes en cuarentena de suplantación de identidad (DefaultFullAccessPolicy). <p> Los administradores pueden crear y seleccionar una directiva de cuarentena personalizada que defina qué destinatarios pueden hacer con estos mensajes en cuarentena. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).|
|**Mostrar el primer contacto consejo de seguridad** <p> _EnableFirstContactSafetyTips_|No seleccionada <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Para obtener más información, vea [First contact consejo de seguridad](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Mostrar (?) para remitentes no autenticados para suplantación de identidad** <p> _EnableUnauthenticatedSender_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|**Mostrar etiqueta "via"** <p> _EnableViaTag_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la **dirección MAIL FROM.** <p> Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|

### <a name="safe-attachments-settings"></a>Caja fuerte de datos adjuntos

Caja fuerte datos adjuntos de Microsoft Defender para Office 365 incluye la configuración global que no tiene ninguna relación con las directivas de datos adjuntos de Caja fuerte y la configuración específica de cada directiva de vínculos Caja fuerte datos adjuntos. Para obtener más información, [vea Caja fuerte Attachments in Defender para Office 365](safe-attachments.md).

Aunque no hay ninguna directiva predeterminada de  datos adjuntos de Caja fuerte, la directiva de seguridad predefinida de protección integrada proporciona protección de datos adjuntos de Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas de datos adjuntos de Caja fuerte personalizadas). Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

#### <a name="global-settings-for-safe-attachments"></a>Configuración global de datos Caja fuerte datos adjuntos

> [!NOTE]
> La configuración global de Caja fuerte datos adjuntos se establece mediante la directiva de  seguridad preestablecida de protección integrada, pero no por las directivas de seguridad predeterminadas **estándar** o estricta.  En cualquier caso, los administradores pueden modificar esta configuración global Caja fuerte datos adjuntos en cualquier momento.
>
> La **columna** Predeterminada muestra los valores antes de la existencia de la **directiva de** seguridad preestablecida de protección integrada. La **columna Protección integrada** muestra los valores establecidos por la directiva de seguridad preestablecida de protección integrada, que también son nuestros valores recomendados. 

Para configurar estas opciones, vea Activar Caja fuerte datos adjuntos para [SharePoint, OneDrive y](turn-on-mdo-for-spo-odb-and-teams.md) Microsoft Teams y [Caja fuerte documentos en Microsoft 365 E5](safe-docs.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Protección integrada|Comentario|
|---|:---:|:---:|---|
|**Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Desactivada <p> `$false`|Activada <p> `$true`|Para evitar que los usuarios descarguen archivos malintencionados, vea [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).|
|**Activar documentos Caja fuerte para Office clientes** <p> _EnableSafeDocs_|Desactivada <p> `$false`|Activada <p> `$true`|Esta característica solo está disponible y significativa con licencias que no se incluyen en Defender para Office 365 (por ejemplo, Microsoft 365 E5 o Seguridad de Microsoft 365 E5). Para obtener más información, [vea Caja fuerte Documents en Microsoft 365 E5](safe-docs.md).|
|**Permitir que las personas haga clic en la vista protegida incluso si Caja fuerte documentos identifican el archivo como malintencionado** <p> _AllowSafeDocsOpen_|Desactivado <p> `$false`|Desactivado <p> `$false`|Esta configuración está relacionada con Caja fuerte documentos.|
|

#### <a name="safe-attachments-policy-settings"></a>Caja fuerte de directiva de datos adjuntos

Para configurar estas opciones, consulte [Configurar Caja fuerte de datos adjuntos en Defender para Office 365](set-up-safe-attachments-policies.md).

En PowerShell, use los cmdlets [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) y [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva Caja fuerte de datos adjuntos predeterminada, pero la directiva de seguridad preestablecida de protección integrada asigna Caja fuerte protección de datos adjuntos a todos los [  destinatarios.](preset-security-policies.md)
>
> La **columna Valor predeterminado en** personalizado hace referencia a los valores predeterminados de las nuevas directivas Caja fuerte datos adjuntos que cree. Las columnas restantes indican (a menos que se indique lo contrario) los valores configurados en las directivas de seguridad preestablecidas correspondientes.

<br>

****

|Nombre de la característica de seguridad|Valor predeterminado en personalizado|Protección integrada|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|:---:|---|
|**Caja fuerte datos adjuntos desconocidos respuesta de malware** <p> _Habilitar_ y _acción_|**Desactivado** <p> `-Enable $false` y `-Action Block`|**Bloquear** <p> `-Enable $true` y `-Action Block`|**Bloquear** <p> `-Enable $true` y `-Action Block`|**Bloquear** <p> `-Enable $true` y `-Action Block`|Cuando el _parámetro Enable_ $false, el valor del _parámetro Action_ no importa.|
|**Directiva de cuarentena** (_QuarantineTag_)|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|Al crear una nueva directiva de datos adjuntos de Caja fuerte, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que Caja fuerte Attachments (AdminOnlyAccessPolicy). <p> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen más funcionalidades para los usuarios. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).|
|**Redirigir datos adjuntos con datos adjuntos** **detectados: habilitar el redireccionamiento** <p> _Redirigir_ <p> _RedirectAddress_|No seleccionado y no se especifica ninguna dirección de correo electrónico. <p> `-Redirect $false` <p> _RedirectAddress_ está en blanco ( `$null` )|No seleccionado y no se especifica ninguna dirección de correo electrónico. <p> `-Redirect $false` <p> _RedirectAddress_ está en blanco ( `$null` )|Seleccionada y especifica una dirección de correo electrónico. <p> `$true` <p> una dirección de correo electrónico|Seleccionada y especifica una dirección de correo electrónico. <p> `$true` <p> una dirección de correo electrónico|Redirigir mensajes a un administrador de seguridad para su revisión. <p> **Nota:** Esta configuración no está configurada en  las directivas de seguridad predeterminadas **de** protección **estándar,** estricta o integrada. Los **valores Estándar** y **Estricto** indican nuestros **valores** recomendados en las nuevas directivas Caja fuerte datos adjuntos que cree.|
|**Aplicar la respuesta Caja fuerte de detección de datos adjuntos si el examen no se puede completar (tiempo de espera o errores)** <p> _ActionOnError_|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|

### <a name="safe-links-settings"></a>Caja fuerte de vínculos

Caja fuerte Vínculos de Defender para Office 365 incluye la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos de Caja fuerte activas y la configuración específica de cada directiva de vínculos de Caja fuerte. Para obtener más información, [vea Caja fuerte Links in Defender for Office 365](safe-links.md).

Aunque no hay ninguna directiva de vínculos  Caja fuerte predeterminada, la directiva de seguridad predefinida de protección integrada proporciona protección de vínculos Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas de vínculos de Caja fuerte personalizadas). Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

#### <a name="global-settings-for-safe-links"></a>Configuración global de Caja fuerte vínculos

> [!NOTE]
> La configuración global de Caja fuerte vínculos  se establece mediante la directiva de seguridad  preestablecida de protección integrada, pero no por las directivas de seguridad predeterminadas **estándar** o estricta. En cualquier caso, los administradores pueden modificar esta configuración global Caja fuerte vínculos en cualquier momento.
>
> La **columna** Predeterminada muestra los valores antes de la existencia de la **directiva de** seguridad preestablecida de protección integrada. La **columna Protección integrada** muestra los valores establecidos por la directiva de seguridad preestablecida de protección integrada, que también son nuestros valores recomendados. 

Para configurar estas opciones, vea [Configure global settings for Caja fuerte Links in Defender for Office 365](configure-global-settings-for-safe-links.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

<br>

****

|Nombre de la característica de seguridad|Predeterminado|Protección integrada|Comentario|
|---|:---:|:---:|---|
|**Bloquear las siguientes direcciones URL** <p> _ExcludedUrls_|En blanco <p> `$null`|En blanco <p> `$null`|No tenemos ninguna recomendación específica para esta configuración. <p> Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para obtener Caja fuerte vínculos](safe-links.md#block-the-following-urls-list-for-safe-links).
|**Usar Caja fuerte vínculos en Office 365 aplicaciones** <p> _EnableSafeLinksForO365Clients_|Activado <p> `$true`|Activado <p> `$true`|Usa Caja fuerte links en aplicaciones Office 365 de escritorio y móviles (iOS y Android). Para obtener más información, [consulta Caja fuerte configuración de vínculos para Office 365 aplicaciones](safe-links.md#safe-links-settings-for-office-365-apps).|
|**No realizar un seguimiento cuando los usuarios hacen clic en vínculos protegidos en Office 365 aplicaciones** <p> _TrackClicks_|Activada <p> `$false`|Desactivada <p> `$true`|Desactivar esta configuración (establecer _TrackClicks_ en ) realiza un seguimiento de los clics del usuario `$true` en las aplicaciones Office 365 compatibles.|
|**No permitir que los usuarios hagan clic en la dirección URL original en Office 365 aplicaciones** <p> _AllowClickThrough_|Activado <p> `$false`|Activado <p> `$false`|Al activar esta configuración (establecer _AllowClickThrough en_ ) se evita hacer clic en la dirección URL original en las `$false` aplicaciones Office 365 compatibles.|
|

#### <a name="safe-links-policy-settings"></a>Caja fuerte de directiva vínculos

Para configurar estas opciones, consulte [Configurar Caja fuerte de vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

En PowerShell, use los [cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) y [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva de vínculos Caja fuerte predeterminada, pero la directiva de seguridad preestablecida de protección integrada asigna la protección de vínculos Caja fuerte todos los [  destinatarios.](preset-security-policies.md)
>
> La **columna Valor predeterminado en personalizado** hace referencia a los valores predeterminados en las nuevas directivas de vínculos Caja fuerte que cree. Las columnas restantes indican (a menos que se indique lo contrario) los valores configurados en las directivas de seguridad preestablecidas correspondientes.

<br>

****

|Nombre de la característica de seguridad|Valor predeterminado en personalizado|Protección integrada|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|:---:|---|
|**Configuración de protección**||||||
|**Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes** <p> _IsEnabled_|**Desactivado** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`|**On** <p> `$true`||
|**Seleccione la acción para direcciones URL desconocidas o potencialmente malintencionadas en Microsoft Teams** <p> _EnableSafeLinksForTeams_|**Desactivado** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`|**On** <p> `$true`||
|**Aplicar análisis de url en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos** <p> _ScanUrls_|No seleccionada <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje** <p> _DeliverMessageAfterScan_|No seleccionada <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**Aplicar Caja fuerte a los mensajes de correo electrónico enviados dentro de la organización** <p> _EnableForInternalSenders_|No seleccionada <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Seleccionado <p> `$true`||
|**No realizar un seguimiento de los clics del usuario** <p> _DoNotTrackUserClicks_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`|Desactivar esta configuración (establecer _DoNotTrackUserClicks_ en `$false` ) realiza un seguimiento de los clics de los usuarios.|
|**No permitir que los usuarios hagan clic en la dirección URL original** <p> _DoNotAllowClickThrough_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|Seleccionado <p> `$true`|Seleccionado <p> `$true`|Al activar esta configuración (al _establecer DoNotAllowClickThrough en_ ) se evita `$true` hacer clic en la dirección URL original.|
|**Mostrar la personal de marca de la organización en las páginas de notificación y advertencia** <p> _EnableOrganizationBranding_|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No seleccionada <p> `$false`|No tenemos ninguna recomendación específica para esta configuración. <p> Antes de activar esta configuración, debes seguir las instrucciones de Personalizar el tema [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) para que la organización cargue el logotipo de la empresa.|
|**No reescriba direcciones URL, realice comprobaciones a través de la API Caja fuerte links solo** <p> _DisableURLRewrite_|No seleccionada <p> `$false`|Seleccionado <p> `$true`|No seleccionada <p> `$false`|No seleccionada <p> `$false`||
|**No reescribir las siguientes direcciones URL** <p> _DoNotRewriteUrls_|No seleccionada <p> en blanco|No seleccionada <p> en blanco|No seleccionada <p> en blanco|No seleccionada <p> en blanco|No tenemos ninguna recomendación específica para esta configuración. Para obtener más información, vea ["Do not rewrite the following URLs" lists in Caja fuerte Links policies](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).|
|**Notificación**||||||
|**¿Cómo le gustaría notificar a los usuarios?**|**Usar el texto de notificación predeterminado**|**Usar el texto de notificación predeterminado**|**Usar el texto de notificación predeterminado**|**Usar el texto de notificación predeterminado**|No tenemos ninguna recomendación específica para esta configuración. <p> Puede seleccionar **Usar texto de notificación personalizado** (_CustomNotificationText_) para escribir el texto de notificación personalizado que se va a usar. También puede seleccionar **Usar Traductor de Microsoft** para la localización automática (_UseTranslatedNotificationText_) para traducir el texto de notificación personalizado al idioma del usuario.
|

## <a name="related-articles"></a>Artículos relacionados

- ¿Está buscando procedimientos recomendados para Exchange de flujo de **correo (también conocidas como reglas de transporte)?** Consulte [Procedimientos recomendados para configurar reglas de flujo](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)de correo en Exchange Online .

- Los administradores y los usuarios pueden enviar falsos positivos (buen correo electrónico marcado como negativo) y falsos negativos (correo electrónico no permitido) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estos vínculos para obtener información sobre cómo **configurar el** servicio [EOP](/exchange/standalone-eop/set-up-your-eop-service)y **configurar** Microsoft Defender [para Office 365](defender-for-office-365.md). No olvide las instrucciones útiles en['Proteger contra amenazas en Office 365'.](protect-against-threats.md)

- **Las líneas** base de seguridad para Windows se pueden encontrar aquí: ¿Dónde puedo obtener las líneas base de [seguridad?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para las opciones de GPO/local y Usar líneas base de seguridad para configurar [dispositivos Windows](/intune/protect/security-baselines) en Intune para la seguridad basada en Intune. Por último, una comparación entre Las líneas base de seguridad de Microsoft Defender para endpoint y Microsoft Intune está disponible en Comparar las líneas base de seguridad de Microsoft Defender para Endpoint y Windows [de seguridad de Intune.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
