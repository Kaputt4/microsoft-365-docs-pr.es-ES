---
title: Recomendaciones de Microsoft para EOP y Defender para Office 365 de seguridad
keywords: Office 365 de seguridad, Marco de directivas de remitente, Informes y conformidad de mensajes basados en dominio, DomainKeys Identified Mail, pasos, cómo funciona, líneas base de seguridad, líneas base para EOP, líneas base para Defender para Office 365 , configurar Defender para Office 365 , configurar EOP, configurar EOP, configurar Defender para Office 365, configurar EOP, configuración de seguridad
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
description: ¿Cuáles son los procedimientos recomendados para Exchange Online Protection (EOP) y Defender para Office 365 de seguridad? ¿Cuáles son las recomendaciones actuales para la protección estándar? ¿Qué se debe usar si quiere ser más estricto? ¿Y qué extras obtienes si también usas Defender para Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4b6c9df3b8c458aaf548ff9c8cfe8cc51fa5824
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507180"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configuración recomendada de seguridad para EOP y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** es el núcleo de seguridad de las suscripciones de Microsoft 365 y ayuda a evitar que los correos malintencionados lleguen a las bandejas de entrada de los empleados. Sin embargo, con ataques nuevos y más sofisticados que surgen cada día, a menudo se requieren protecciones mejoradas. **Microsoft Defender para Office 365** plan 1 o plan 2 contienen características adicionales que dan a los administradores más capas de seguridad, control e investigación.

Aunque habilitamos a los administradores de seguridad para personalizar su configuración de seguridad, hay dos niveles de seguridad en EOP y Microsoft Defender para Office 365 que recomendamos: **Estándar** y **Estricto**. Aunque los entornos y las necesidades de los clientes son diferentes, estos niveles de filtrado ayudarán a evitar que el correo no deseado llegue a la Bandeja de entrada de los empleados en la mayoría de las situaciones.

Para aplicar automáticamente la configuración Estándar o Estricta a los usuarios, consulte Preestablecidas directivas de seguridad en [EOP y Microsoft Defender para Office 365](preset-security-policies.md).

En este artículo se describe la configuración predeterminada y también la configuración estándar y estricta recomendada para ayudar a proteger a los usuarios. Las tablas contienen la configuración del portal de Microsoft 365 Defender y PowerShell (Exchange Online PowerShell o powershell independiente Exchange Online Protection powershell para organizaciones sin Exchange Online buzones de correo).

> [!TIP]
> No puede cambiar la configuración estándar y estricta recomendada en el portal Microsoft 365 Defender web. Para cambiar los valores recomendados, como **Permitir que los** usuarios protejan, debe usar [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
>
> El Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) para PowerShell puede ayudarle (administradores) a encontrar los valores actuales de esta configuración. En concreto, el cmdlet **Get-ORCAReport** genera una evaluación de la configuración contra correo no deseado, contra suplantación de identidad (phishing) y otras opciones de higiene de mensajes. Puede descargar el módulo ORCA en <https://www.powershellgallery.com/packages/ORCA/>.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protección contra correo no deseado, antimalware y anti phishing en EOP

El correo no deseado, el antimalware y la suplantación de identidad (phishing) son características de EOP que pueden configurar los administradores. Se recomiendan las siguientes configuraciones estándar o estrictas.

### <a name="eop-anti-spam-policy-settings"></a>Configuración de directiva contra correo no deseado de EOP

Para crear y configurar directivas contra correo no deseado, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbral de correo electrónico masivo & de correo no deseado**|||||
|**Umbral de correo electrónico masivo** <br/><br/> _BulkThreshold_|7 |6 |4|Para obtener más información, [consulte Nivel de queja masiva (BCL) en EOP](bulk-complaint-level-values.md).|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|Esta configuración solo está disponible en PowerShell.|
|**Aumentar la configuración de puntuación de correo** no deseado|Desactivado|Desactivado|Desactivado|Todas estas opciones de configuración forman parte del filtro de correo no deseado avanzado (ASF). Para obtener más información, vea la sección [Configuración de ASF en directivas contra correo](#asf-settings-in-anti-spam-policies) no deseado en este artículo.|
|**Marcar como configuración de correo** no deseado|Desactivado|Desactivado|Desactivado|La mayoría de estas opciones de configuración forman parte de ASF. Para obtener más información, vea la sección [Configuración de ASF en directivas contra correo](#asf-settings-in-anti-spam-policies) no deseado en este artículo.|
|**Contiene idiomas específicos** <br/><br/> _EnableLanguageBlockList_ <br/><br/> _LanguageBlockList_|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|**Desactivado** <br/><br/> `$false` <br/><br/> En blanco|**Desactivada** <br/><br/> `$false` <br/><br/> En blanco|No tenemos ninguna recomendación específica para esta configuración. Puede bloquear mensajes en idiomas específicos en función de sus necesidades empresariales.|
|**Desde estos países** <br/><br/> _EnableRegionBlockList_ <br/><br/> _RegionBlockList_|**Desactivada** <br/><br/> `$false` <br/><br/> En blanco|**Desactivada** <br/><br/> `$false` <br/><br/> En blanco|**Desactivada** <br/><br/> `$false` <br/><br/> En blanco|No tenemos ninguna recomendación específica para esta configuración. Puede bloquear mensajes de países específicos en función de sus necesidades empresariales.|
|**Modo de prueba** (_TestModeAction_)|**Ninguna**|**Ninguna**|**Ninguna**|Esta configuración forma parte de ASF. Para obtener más información, vea la sección [Configuración de ASF en directivas contra correo](#asf-settings-in-anti-spam-policies) no deseado en este artículo.|
|**Acciones**||||Siempre que seleccione **Un mensaje de cuarentena**, hay disponible **un cuadro Seleccionar directiva de** cuarentena. Las directivas de cuarentena definen lo que los usuarios pueden hacer en los mensajes en cuarentena. <br/><br/> Al crear una nueva directiva contra correo no deseado, un valor en blanco significa que la directiva de cuarentena predeterminada se usa para definir las capacidades históricas de los mensajes que fueron puestos en cuarentena por ese veredicto en particular (AdminOnlyAccessPolicy para **phishing** de elevada confianza; DefaultFullAccessPolicy para todo lo demás). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen capacidades más restrictivas o menos restrictivas para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Acción de detección de correo** no deseado <br/><br/> _SpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|**Acción de detección de correo no deseado** de elevada confianza <br/><br/> _HighConfidenceSpamAction_|**Colocar el mensaje en cuarentena** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|**Acción de detección de phishing** <br/><br/> _PhishSpamAction_|**Colocar el mensaje en cuarentena** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|**Acción de detección de phishing de elevada** confianza <br/><br/> _HighConfidencePhishAction_|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|**Acción de** detección masiva <br/><br/> _BulkSpamAction_|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Mover mensaje a la carpeta Correo no deseado** <br/><br/> `MoveToJmf`|**Colocar el mensaje en cuarentena** <br/><br/> `Quarantine`||
|**Conservar el correo no deseado en cuarentena durante estos días** <br/><br/> _QuarantineRetentionPeriod_|15 días<sup>\*</sup>|30 días|30 días|<sup>\*</sup> El valor predeterminado es 15 días en la directiva contra correo no deseado predeterminada y en las nuevas directivas contra correo no deseado que cree en PowerShell. El valor predeterminado es 30 días en las nuevas directivas contra correo no deseado que cree en el portal de Microsoft 365 Defender. <br/><br/> Este valor también afecta a los mensajes que están en cuarentena mediante directivas contra suplantación de identidad. Para obtener más información, vea [Mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).|
|**Habilitar sugerencias de seguridad contra correo no deseado** <br/><br/> _InlineSafetyTipsEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|Habilitar la purga automática de hora cero (ZAP) para mensajes de suplantación de identidad <br/><br/> _PhishZapEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|Habilitar ZAP para mensajes de correo no deseado <br/><br/> _SpamZapEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Permitir & de bloques**|||||
|Remitentes permitidos <br/><br/> _AllowedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente permitidos <br/><br/> _AllowedSenderDomains_|Ninguno|Ninguno|Ninguno|Agregar dominios a la lista de remitentes permitidos es una idea muy mala. Los atacantes podrían enviarle un correo electrónico que, de lo contrario, se filtraría. <br/><br/> Use la [](learn-about-spoof-intelligence.md) información de inteligencia de suplantación de identidad y la lista de permitidos [o](tenant-allow-block-list.md) bloqueados de inquilinos para revisar todos los remitentes que suplanten direcciones de correo electrónico de remitente en los dominios de correo electrónico de su organización o suplanten direcciones de correo electrónico de remitente en dominios externos.|
|Remitentes bloqueados <br/><br/> _BlockedSenders_|Ninguno|Ninguno|Ninguno||
|Dominios de remitente bloqueados <br/><br/> _BlockedSenderDomains_|Ninguno|Ninguno|Ninguno||

#### <a name="asf-settings-in-anti-spam-policies"></a>Configuración de ASF en directivas contra correo no deseado

En la tabla de esta sección se describe la configuración del filtro de correo no deseado avanzado (ASF) que están disponibles en las directivas contra correo no deseado. Todas estas opciones de configuración están **desactivadas** para **los niveles Estándar** **y** Estricto. Para obtener más información acerca de la configuración de ASF, consulte [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).

|Nombre de la característica de seguridad|Comentario|
|---|---|
|**Vínculos de imagen a sitios remotos** (_IncreaseScoreWithImageLinks_)||
|**Dirección IP numérica en dirección URL** (_IncreaseScoreWithNumericIps_)||
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
|**Registro SPF: error (**_MarkAsSpamSpfRecordHardFail_)||
|**Error de filtrado de id. de remitente** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|**Modo de prueba** (_TestModeAction_)|Para las opciones de ASF que admiten **Probar** como acción, puede configurar la acción del modo de prueba en **Ninguno**, Agregar texto predeterminado de **encabezado X** o Enviar mensaje **CCO** (`None`, `AddXHeader`o `BccMessage`). Para obtener más información, vea [Habilitar, deshabilitar o probar la configuración de ASF](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings).|

#### <a name="eop-outbound-spam-policy-settings"></a>Configuración de directiva de correo no deseado saliente de EOP

Para crear y configurar directivas de correo no deseado salientes, consulte [Configurar el filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md).

Para obtener más información acerca de los límites de envío predeterminados en el servicio, vea [Límites de envío](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

> [!NOTE]
> Las directivas de correo no deseado saliente no forman parte de directivas de seguridad predeterminadas estándar o estrictas. Los **valores Estándar** y **Estricto** indican nuestros **valores recomendados** en la directiva de correo no deseado saliente predeterminada o las directivas personalizadas que cree.

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Establecer un límite de mensajes externos** <br/><br/> _RecipientLimitExternalPerHour_|0|500|400|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Establecer un límite de mensajes interno** <br/><br/> _RecipientLimitInternalPerHour_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Establecer un límite de mensajes diario** <br/><br/> _RecipientLimitPerDay_|0|1000|800|El valor predeterminado 0 significa usar los valores predeterminados del servicio.|
|**Restricción impuesta a los usuarios que alcanzan el límite de mensajes** <br/><br/> _ActionWhenThresholdReached_|**Restringir al usuario el envío de correo hasta el día siguiente** <br/><br/> `BlockUserForToday`|**Restringir al usuario el envío de correo** <br/><br/> `BlockUser`|**Restringir al usuario el envío de correo** <br/><br/> `BlockUser`||
|**Reglas de reenvío automático** <br/><br/> _AutoForwardingMode_|**Automático: controlado por el sistema** <br/><br/> `Automatic`|**Automático: controlado por el sistema** <br/><br/> `Automatic`|**Automático: controlado por el sistema** <br/><br/> `Automatic`|
|**Enviar una copia de mensajes salientes que superen estos límites a estos usuarios y grupos** <br/><br/> _BccSuspiciousOutboundMail_ <br/><br/> _BccSuspiciousOutboundAdditionalRecipients_|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Esta configuración solo funciona en la directiva de correo no deseado saliente predeterminada. No funciona en las directivas de correo no deseado saliente personalizadas que cree.|
|**Notificar a estos usuarios y grupos si un remitente está bloqueado debido al envío de correo no deseado saliente** <br/><br/> _NotifyOutboundSpam_ <br/><br/> _NotifyOutboundSpamRecipients_|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|No seleccionada <br/><br/> `$false` <br/><br/> En blanco|La [directiva de](../../compliance/alert-policies.md) alerta predeterminada  denominada Usuario restringido para enviar correo electrónico ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (administradores globales) cuando los usuarios se bloquean debido a que superan los **límites** de la directiva. **Se recomienda encarecidamente que use la directiva de** alertas en lugar de esta configuración en la directiva de correo no deseado saliente para notificar a los administradores y otros usuarios. Para obtener instrucciones, consulte [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).|

### <a name="eop-anti-malware-policy-settings"></a>Configuración de directiva antimalware de EOP

Para crear y configurar directivas antimalware, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Configuración de protección**|||||
|**Habilitar el filtro de datos adjuntos común** <br/><br/> _EnableFileFilter_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Esta configuración pone en cuarentena los mensajes que contienen datos adjuntos ejecutables según el tipo de archivo, independientemente del contenido de los datos adjuntos.|
|**Habilitar la purga automática de hora cero para malware** <br/><br/> _ZapEnabled_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Directiva de cuarentena**|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|Al crear una nueva directiva antimalware, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena como malware (AdminOnlyAccessPolicy). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen más funcionalidades para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Notificaciones de destinatarios**|||||
|**Notificar a los destinatarios cuando los mensajes se ponen en cuarentena como malware** <br/><br/> _Action_|No seleccionada <br/><br/> _DeleteMessage_|No seleccionada <br/><br/> _DeleteMessage_|No seleccionada <br/><br/> _DeleteMessage_|Si se detecta malware en un archivo adjunto de correo electrónico, el mensaje se pone en cuarentena y solo puede publicarlo un administrador.|
|**Notificaciones de remitente**|||||
|**Notificar a los remitentes internos cuando los mensajes se ponen en cuarentena como malware** <br/><br/> _EnableInternalSenderNotifications_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**Notificar a remitentes externos cuando los mensajes se ponen en cuarentena como malware** <br/><br/> _EnableExternalSenderNotifications_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**Notificaciones de administrador**|||||
|**Notificar a un administrador sobre los mensajes no entregados de remitentes internos** <br/><br/> _EnableInternalSenderAdminNotifications_ <br/><br/> _InternalSenderAdminAddress_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No tenemos ninguna recomendación específica para esta configuración.|
|**Notificar a un administrador sobre los mensajes no entregados de remitentes externos** <br/><br/> _EnableExternalSenderAdminNotifications_ <br/><br/> _ExternalSenderAdminAddress_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No tenemos ninguna recomendación específica para esta configuración.|
|**Personalizar notificaciones**||||No tenemos recomendaciones específicas para esta configuración.|
|**Usar texto de notificación personalizado** <br/><br/> _CustomNotifications_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**Nombre De** <br/><br/> _CustomFromName_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Dirección de origen** <br/><br/> _CustomFromAddress_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Personalizar notificaciones para mensajes de remitentes internos**||||Esta configuración solo se usa si se selecciona **Notificar a remitentes** internos cuando los mensajes se ponen en cuarentena como malware o notificar a un administrador sobre los mensajes no **entregados de remitentes** internos.|
|**Subject** <br/><br/> _CustomInternalSubject_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Message** <br/><br/> _CustomInternalBody_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Personalizar notificaciones para mensajes de remitentes externos**||||Esta configuración solo se usa si se selecciona **Notificar a remitentes externos** cuando los mensajes se ponen en cuarentena como malware o notificar a un administrador sobre los mensajes no **entregados de remitentes externos** .|
|**Asunto** <br/><br/> _CustomExternalSubject_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||
|**Message** <br/><br/> _CustomExternalBody_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`||

### <a name="eop-anti-phishing-policy-settings"></a>Configuración de directiva contra suplantación de identidad de EOP

Para obtener más información acerca de esta configuración, consulte [Configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings). Para configurar estas opciones, consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección contra & de phishing**|||||
|**Habilitar la inteligencia de suplantación** <br/><br/> _EnableSpoofIntelligence_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Acciones**|||||
|**Si el mensaje se detecta como suplantación** <br/><br/> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Esta configuración se aplica a remitentes suplantados que se bloquearon automáticamente, como se muestra en [](learn-about-spoof-intelligence.md) la información de inteligencia de suplantación de identidad o bloqueados manualmente en la lista de inquilinos [permitidos o bloqueados](tenant-allow-block-list.md). <br/><br/> Si selecciona **Poner** en cuarentena el mensaje,  hay disponible un cuadro Aplicar directiva de cuarentena para seleccionar la directiva de cuarentena que define lo que los usuarios pueden hacer a los mensajes que se ponen en cuarentena como suplantación. Al crear una nueva directiva anti phishing, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena como suplantación de identidad (DefaultFullAccessPolicy). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen capacidades más restrictivas o menos restrictivas para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Mostrar el primer contacto consejo de seguridad** <br/><br/> _EnableFirstContactSafetyTips_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|Para obtener más información, vea [First contact consejo de seguridad](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Mostrar (?) para remitentes no autenticados para suplantación de identidad** <br/><br/> _EnableUnauthenticatedSender_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|**Mostrar etiqueta "via"** <br/><br/> _EnableViaTag_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la dirección **MAIL FROM** . <br/><br/> Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender para Office 365 seguridad

Las ventajas de seguridad adicionales vienen con una Microsoft Defender para Office 365 suscripción. Para obtener las últimas noticias e información, puede ver [Novedades de Defender para Office 365](whats-new-in-defender-for-office-365.md).

> [!IMPORTANT]
>
> - La directiva contra suplantación de identidad predeterminada en Microsoft Defender para Office 365 proporciona protección [contra](set-up-anti-phishing-policies.md#spoof-settings) suplantación de identidad e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras [características de](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) protección de suplantación disponibles y la configuración [avanzada no están](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva contra suplantación de identidad predeterminada o cree directivas adicionales contra la suplantación de identidad.
>
> - Aunque no hay ninguna directiva de datos adjuntos de Caja fuerte predeterminada o una directiva de vínculos de Caja fuerte,  la directiva de seguridad predefinida de protección integrada proporciona protección de datos adjuntos de Caja fuerte y protección de vínculos Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas de datos adjuntos de Caja fuerte personalizadas o Caja fuerte de vínculos). Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender para Office 365](preset-security-policies.md).
>
> - [Caja fuerte datos adjuntos para SharePoint, OneDrive y](mdo-for-spo-odb-and-teams.md) protección Microsoft Teams y protección de documentos Caja fuerte no tienen dependencias en [](safe-docs.md) las directivas Caja fuerte vínculos.

Si la suscripción incluye Microsoft Defender para Office 365 o si has comprado Defender para Office 365 como complemento, establece las siguientes configuraciones Estándar o Estricta.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directiva contra suplantación de identidad en Microsoft Defender para Office 365

Los clientes de EOP obtienen la protección contra suplantación de identidad básica como se describió anteriormente, pero Defender para Office 365 incluye más características y control para ayudar a prevenir, detectar y corregir los ataques. Para crear y configurar estas directivas, consulte [Configure anti-phishing policies in Defender para Office 365](configure-mdo-anti-phishing-policies.md).

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración avanzada en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, consulte [Umbrales de suplantación de identidad avanzados en directivas contra suplantación de identidad en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar esta configuración, consulte [Configure anti-phishing policies in Defender para Office 365](configure-mdo-anti-phishing-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Umbral de correo electrónico de suplantación de identidad** <br/><br/> _PhishThresholdLevel_|**1- Estándar** <br/><br/> `1`|**2 : agresivo** <br/><br/> `2`|**3: más agresivo** <br/><br/> `3`||

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Para obtener más información acerca de esta configuración, vea Configuración de suplantación [en directivas contra suplantación en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar estas opciones, consulte [Configure anti-phishing policies in Defender para Office 365](configure-mdo-anti-phishing-policies.md).

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección contra & de phishing**|||||
|**Permitir a los usuarios proteger** (protección de usuario suplantada) <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|No seleccionada <br/><br/> `$false` <br/><br/> ninguno|Seleccionado <br/><br/> `$true` <br/><br/> \<list of users\>|Seleccionado <br/><br/> `$true` <br/><br/> \<list of users\>|Se recomienda agregar usuarios (remitentes de mensajes) en roles clave. Internamente, los remitentes protegidos pueden ser su director general, director financiero y otros líderes sénior. Externamente, los remitentes protegidos podrían incluir miembros del consejo o su junta directiva. <br/><br/> En las directivas de seguridad preestablecidas, no se pueden especificar los usuarios que se deben proteger. Debes deshabilitar las directivas de seguridad preestablecidas y usar directivas personalizadas contra suplantación de identidad para agregar usuarios a roles clave como se sugiere.|
|**Habilitar dominios para proteger** (protección de dominio suplantada)|No seleccionada|Seleccionado|Seleccionado||
|**Incluir dominios de mi propiedad** <br/><br/> _EnableOrganizationDomainsProtection_|Desactivado <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Incluir dominios personalizados** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Desactivada <br/><br/> `$false` <br/><br/> ninguno|Seleccionado <br/><br/> `$true` <br/><br/> \<list of domains\>|Seleccionado <br/><br/> `$true` <br/><br/> \<list of domains\>|Se recomienda agregar dominios (dominios de remitente) que no posee, pero con los que interactúa con frecuencia. <br/><br/> En las directivas de seguridad preestablecidas, no puede especificar los dominios custm que se deben proteger. Debes deshabilitar las directivas de seguridad preestablecidas y usar directivas personalizadas contra suplantación de identidad para agregar dominios personalizados para proteger como se sugiere.|
|**Agregar dominios y remitentes de confianza** <br/><br/> _ExcludedSenders_ <br/><br/> _ExcludedDomains_|Ninguno|Ninguno|Ninguno|Según la organización, se recomienda agregar remitentes o dominios que se identifiquen incorrectamente como intentos de suplantación.|
|**Habilitar la inteligencia de buzones** <br/><br/> _EnableMailboxIntelligence_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Habilitar la inteligencia para la protección de suplantación** <br/><br/> _EnableMailboxIntelligenceProtection_|Desactivada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Esta configuración permite la acción especificada para las detecciones de suplantación por inteligencia de buzones.|
|**Acciones**||||Siempre que seleccione **Poner en cuarentena el mensaje**, hay disponible **un cuadro Seleccionar directiva de** cuarentena. Las directivas de cuarentena definen lo que los usuarios pueden hacer en los mensajes en cuarentena. <br/><br/> Al crear una nueva directiva anti phishing, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena por ese veredicto (DefaultFullAccessPolicy para todos los tipos de detección de suplantación). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen capacidades menos restrictivas o más restrictivas para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Si el mensaje se detecta como un usuario suplantado** <br/><br/> _TargetedUserProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Recuerde que las directivas de seguridad preestablecidas no permiten especificar los usuarios que se van a proteger, por lo que esta configuración no hace nada en las directivas de seguridad predefinidas.|
|**Si el mensaje se detecta como un dominio suplantado** <br/><br/> _TargetedDomainProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Recuerde que las directivas de seguridad preestablecidas no permiten especificar los dominios personalizados que se protegerán, por lo que esta configuración solo afecta a los dominios de su propiedad, no a los dominios personalizados.|
|**Si la inteligencia de buzones detecta y suplanta al usuario** <br/><br/> _MailboxIntelligenceProtectionAction_|**No aplicar ninguna acción** <br/><br/> `NoAction`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`||
|**Mostrar la suplantación de usuario consejo de seguridad** <br/><br/> _EnableSimilarUsersSafetyTips_|Desactivada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Mostrar la suplantación de dominio consejo de seguridad** <br/><br/> _EnableSimilarDomainsSafetyTips_|Desactivada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Mostrar caracteres inusuales de suplantación de usuario consejo de seguridad** <br/><br/> _EnableUnusualCharactersSafetyTips_|Desactivada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configuración de directiva contra suplantación de identidad de EOP en Microsoft Defender para Office 365

Estas son las mismas opciones que están disponibles en la [configuración de directiva contra correo no deseado en EOP](#eop-anti-spam-policy-settings).

La configuración de suplantación de dominio está interrelacionado, pero la configuración Mostrar primer contacto consejo de seguridad no depende de la configuración de suplantación.

|Nombre de la característica de seguridad|Predeterminado|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|---|
|**Protección contra & de phishing**|||||
|**Habilitar la inteligencia de suplantación** <br/><br/> _EnableSpoofIntelligence_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Acciones**|||||
|**Si el mensaje se detecta como suplantación** <br/><br/> _AuthenticationFailAction_|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Mover el mensaje a las carpetas de correo no deseado de los destinatarios** <br/><br/> `MoveToJmf`|**Poner en cuarentena el mensaje** <br/><br/> `Quarantine`|Esta configuración se aplica a remitentes suplantados que se bloquearon automáticamente, como se muestra en [](learn-about-spoof-intelligence.md) la información de inteligencia de suplantación de identidad o bloqueados manualmente en la lista de inquilinos [permitidos o bloqueados](tenant-allow-block-list.md). <br/><br/> Si selecciona **Poner en cuarentena el** mensaje,  hay disponible un cuadro Aplicar directiva de cuarentena para seleccionar la directiva de cuarentena que define lo que los usuarios pueden hacer con los mensajes en cuarentena. Al crear una nueva directiva anti phishing, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes en cuarentena de suplantación de identidad (DefaultFullAccessPolicy). <br/><br/> Los administradores pueden crear y seleccionar una directiva de cuarentena personalizada que defina qué destinatarios pueden hacer con estos mensajes en cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Mostrar el primer contacto consejo de seguridad** <br/><br/> _EnableFirstContactSafetyTips_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Para obtener más información, vea [First contact consejo de seguridad](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Mostrar (?) para remitentes no autenticados para suplantación de identidad** <br/><br/> _EnableUnauthenticatedSender_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Agrega un signo de interrogación (?) a la foto del remitente en Outlook para remitentes suplantados no identificados. Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|**Mostrar etiqueta "via"** <br/><br/> _EnableViaTag_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la dirección **MAIL FROM** . <br/><br/> Para obtener más información, vea [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|

### <a name="safe-attachments-settings"></a>Caja fuerte de datos adjuntos

Caja fuerte datos adjuntos de Microsoft Defender para Office 365 incluye la configuración global que no tiene ninguna relación con las directivas de datos adjuntos de Caja fuerte y la configuración específica de cada directiva de vínculos de Caja fuerte. Para obtener más información, [vea Caja fuerte datos adjuntos en Defender para Office 365](safe-attachments.md).

Aunque no hay ninguna directiva predeterminada de datos adjuntos de Caja fuerte, la  directiva de seguridad predefinida de protección integrada proporciona protección de datos adjuntos Caja fuerte todos los destinatarios (usuarios que no están definidos en directivas de datos adjuntos de Caja fuerte personalizadas). Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender para Office 365](preset-security-policies.md).

#### <a name="global-settings-for-safe-attachments"></a>Configuración global de datos adjuntos Caja fuerte datos adjuntos

> [!NOTE]
> La configuración global de Caja fuerte datos adjuntos se establece mediante la directiva de seguridad preestablecida de protección integrada, pero no  por las  directivas de seguridad predeterminadas estándar o estricta. En cualquier caso, los administradores pueden modificar esta configuración global Caja fuerte datos adjuntos en cualquier momento.
>
> La **columna** Predeterminada muestra los valores antes de la existencia de la **directiva de** seguridad preestablecida de protección integrada. La **columna Protección integrada** muestra los valores establecidos por la directiva de seguridad **preestablecida** de protección integrada, que también son nuestros valores recomendados.

Para configurar estas opciones, consulte Activar Caja fuerte datos adjuntos para [SharePoint, OneDrive y](turn-on-mdo-for-spo-odb-and-teams.md) Microsoft Teams y [Caja fuerte documentos en Microsoft 365 E5](safe-docs.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

|Nombre de la característica de seguridad|Predeterminado|Protección integrada|Comentario|
|---|:---:|:---:|---|
|**Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams** <br/><br/> _EnableATPForSPOTeamsODB_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Para evitar que los usuarios descarguen archivos malintencionados, [vea Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).|
|**Activar documentos Caja fuerte para Office clientes** <br/><br/> _EnableSafeDocs_|Desactivada <br/><br/> `$false`|Activada <br/><br/> `$true`|Esta característica solo está disponible y significativa con licencias que no se incluyen en Defender para Office 365 (por ejemplo, Microsoft 365 E5 o Seguridad de Microsoft 365 E5). Para obtener más información, [vea Caja fuerte Documents in Microsoft 365 E5](safe-docs.md).|
|**Permitir que los usuarios haga clic en la vista protegida incluso si Caja fuerte documentos identifican el archivo como malintencionado** <br/><br/> _AllowSafeDocsOpen_|Desactivada <br/><br/> `$false`|Desactivado <br/><br/> `$false`|Esta configuración está relacionada con Caja fuerte documentos.|

#### <a name="safe-attachments-policy-settings"></a>Caja fuerte de directiva de datos adjuntos

Para configurar estas opciones, consulte [Configurar Caja fuerte de datos adjuntos en Defender para Office 365](set-up-safe-attachments-policies.md).

En PowerShell, use los cmdlets [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) y [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se ha descrito anteriormente, no hay ninguna directiva Caja fuerte de datos adjuntos predeterminada, pero la directiva de seguridad preestablecida de protección integrada asigna Caja fuerte protección de datos adjuntos a todos los [ destinatarios](preset-security-policies.md).
>
> La **columna Valor predeterminado en personalizado** hace referencia a los valores predeterminados en las nuevas directivas Caja fuerte datos adjuntos que cree. Las columnas restantes indican (a menos que se indique lo contrario) los valores configurados en las directivas de seguridad preestablecidas correspondientes.

|Nombre de la característica de seguridad|Valor predeterminado en personalizado|Protección integrada|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|:---:|---|
|**Caja fuerte datos adjuntos respuesta de malware desconocido** <br/><br/> _Habilitar_ y _acción_|**Desactivada** <br/><br/> `-Enable $false` y `-Action Block`|**Bloquear** <br/><br/> `-Enable $true` y `-Action Block`|**Bloquear** <br/><br/> `-Enable $true` y `-Action Block`|**Bloquear** <br/><br/> `-Enable $true` y `-Action Block`|Cuando el _parámetro Enable_ $false, el valor del _parámetro Action_ no importa.|
|**Directiva de cuarentena** (_QuarantineTag_)|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|Al crear una nueva directiva de datos adjuntos de Caja fuerte, un valor en blanco significa que se usa la directiva de cuarentena predeterminada para definir las capacidades históricas de los mensajes que se han puesto en cuarentena por Caja fuerte Attachments (AdminOnlyAccessPolicy). <br/><br/> Los administradores pueden crear y seleccionar directivas de cuarentena personalizadas que definen más funcionalidades para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).|
|**Redirigir datos adjuntos con datos adjuntos** **detectados: habilitar el redireccionamiento** <br/><br/> _Redirigir_ <br/><br/> _RedirectAddress_|No seleccionado y no se especifica ninguna dirección de correo electrónico. <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress_ está en blanco (`$null`)|No seleccionado y no se especifica ninguna dirección de correo electrónico. <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress_ está en blanco (`$null`)|Seleccionada y especifica una dirección de correo electrónico. <br/><br/> `$true` <br/><br/> una dirección de correo electrónico|Seleccionada y especifica una dirección de correo electrónico. <br/><br/> `$true` <br/><br/> una dirección de correo electrónico|Redirigir mensajes a un administrador de seguridad para su revisión. <br/><br/> **Nota**: Esta configuración no está configurada en las directivas de seguridad predeterminadas  de protección **estándar, estricta** o integrada. Los **valores Estándar** y **Estricto** indican nuestros **valores recomendados** en las nuevas directivas Caja fuerte datos adjuntos que cree.|
|**Aplicar la respuesta Caja fuerte de detección de datos adjuntos si el examen no se puede completar (tiempo de espera o errores)** <br/><br/> _ActionOnError_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||

### <a name="safe-links-settings"></a>Caja fuerte de vínculos

Caja fuerte vínculos de Defender para Office 365 incluye la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos de Caja fuerte activas y la configuración específica de cada directiva de vínculos de Caja fuerte. Para obtener más información, [vea Caja fuerte links in Defender para Office 365](safe-links.md).

Aunque no hay ninguna directiva predeterminada de vínculos de Caja fuerte, la directiva  de seguridad predefinida de protección integrada proporciona protección de vínculos Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas de vínculos de Caja fuerte personalizadas). Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender para Office 365](preset-security-policies.md).

#### <a name="global-settings-for-safe-links"></a>Configuración global de Caja fuerte vínculos

> [!NOTE]
> La configuración global de Caja fuerte vínculos se establece mediante la directiva de  seguridad preestablecida de protección integrada, pero no por las directivas  de seguridad predeterminadas **estándar** o estricta. En cualquier caso, los administradores pueden modificar esta configuración global Caja fuerte vínculos en cualquier momento.
>
> La **columna** Predeterminada muestra los valores antes de la existencia de la **directiva de** seguridad preestablecida de protección integrada. La **columna Protección integrada** muestra los valores establecidos por la directiva de seguridad **preestablecida** de protección integrada, que también son nuestros valores recomendados.

Para configurar estas opciones, consulte [Configure global settings for Caja fuerte Links in Defender para Office 365](configure-global-settings-for-safe-links.md).

En PowerShell, use el cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para esta configuración.

|Nombre de la característica de seguridad|Predeterminado|Protección integrada|Comentario|
|---|:---:|:---:|---|
|**Bloquear las siguientes direcciones URL** <br/><br/> _ExcludedUrls_|En blanco <br/><br/> `$null`|En blanco <br/><br/> `$null`|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para obtener Caja fuerte vínculos](safe-links.md#block-the-following-urls-list-for-safe-links).
|**Usar Caja fuerte vínculos en Office 365 aplicaciones** <br/><br/> _EnableSafeLinksForO365Clients_|Activado <br/><br/> `$true`|Activada <br/><br/> `$true`|Usa Caja fuerte vínculos en aplicaciones Office 365 de escritorio y móviles (iOS y Android). Para obtener más información, [consulta Caja fuerte de vínculos para Office 365 aplicaciones](safe-links.md#safe-links-settings-for-office-365-apps).|
|**No realizar un seguimiento cuando los usuarios hacen clic en vínculos protegidos en Office 365 aplicaciones** <br/><br/> _TrackClicks_|Activada <br/><br/> `$false`|Desactivada <br/><br/> `$true`|Desactivar esta configuración (establecer _TrackClicks_ en `$true`) realiza un seguimiento de los clics del usuario en las aplicaciones Office 365 compatibles.|
|**No permitir que los usuarios hagan clic en la dirección URL original en Office 365 aplicaciones** <br/><br/> _AllowClickThrough_|Activado <br/><br/> `$false`|Activada <br/><br/> `$false`|Al activar esta configuración (establecer _AllowClickThrough en_ `$false`) se evita hacer clic en la dirección URL original en las aplicaciones Office 365 compatibles.|

#### <a name="safe-links-policy-settings"></a>Configuración de directiva de vínculos seguros

Para configurar estas opciones, consulte [Configurar Caja fuerte directivas de vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

En PowerShell, use los [cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) y [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) para esta configuración.

> [!NOTE]
> Como se describió anteriormente, no hay ninguna directiva de vínculos Caja fuerte predeterminada, pero la directiva de seguridad predefinida de protección integrada asigna la protección de vínculos Caja fuerte todos los [ destinatarios](preset-security-policies.md).
>
> La **columna Valor predeterminado en** personalizado hace referencia a los valores predeterminados en las nuevas directivas de vínculos Caja fuerte que cree. Las columnas restantes indican (a menos que se indique lo contrario) los valores configurados en las directivas de seguridad preestablecidas correspondientes.

|Nombre de la característica de seguridad|Valor predeterminado en personalizado|Protección integrada|Estándar|Estricto|Comentario|
|---|:---:|:---:|:---:|:---:|---|
|**Url & configuración de protección de clics**||||||
|**Acción en direcciones URL potencialmente malintencionadas dentro de correos electrónicos**||||||
|**On: Caja fuerte Links comprueba una lista de vínculos conocidos y malintencionados cuando los usuarios hacen clic en vínculos en el correo electrónico** <br/><br/> _EnableSafeLinksForEmail_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Aplicar Caja fuerte vínculos a mensajes de correo electrónico enviados dentro de la organización** <br/><br/> _EnableForInternalSenders_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Aplicar análisis de url en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos** <br/><br/> _ScanUrls_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje** <br/><br/> _DeliverMessageAfterScan_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**No reescriba direcciones URL, realice comprobaciones a través de la API Caja fuerte links solo** <br/><br/> _DisableURLRewrite_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`||
|**No reescribir las siguientes direcciones URL en el correo electrónico** <br/><br/> _DoNotRewriteUrls_|No seleccionada <br/><br/> en blanco|No seleccionada <br/><br/> en blanco|No seleccionada <br/><br/> en blanco|No seleccionada <br/><br/> en blanco|No tenemos ninguna recomendación específica para esta configuración. Para obtener más información, vea ["Do not rewrite the following URLs" lists in Caja fuerte Links policies](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).|
|**Acción para direcciones URL potencialmente malintencionadas en Microsoft Teams**||||||
|**On: Caja fuerte Links comprueba una lista de vínculos conocidos y malintencionados cuando los usuarios hacen clic en vínculos en Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|No seleccionada <br/><br/> `$false`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Hacer clic en configuración de protección**||||||
|**Realizar un seguimiento de los clics del usuario** <br/><br/> _TrackUserClicks_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`||
|**Permitir a los usuarios hacer clic en la dirección URL original** <br/><br/> _AllowClickThrough_|Seleccionado <br/><br/> `$true`|Seleccionado <br/><br/> `$true`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|Desactivar esta configuración (establecer _AllowClickThrough en_ `$false`) impide hacer clic en la dirección URL original.|
|**Mostrar la personal de marca de la organización en las páginas de notificación y advertencia** <br/><br/> _EnableOrganizationBranding_|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No seleccionada <br/><br/> `$false`|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Antes de activar esta configuración, debes seguir las instrucciones [de Personalizar el tema Microsoft 365 de](../../admin/setup/customize-your-organization-theme.md) la organización para cargar el logotipo de la empresa.|
|**Notificación**||||||
|**¿Cómo le gustaría notificar a los usuarios?**|**Usar el texto de notificación predeterminado**|**Usar el texto de notificación predeterminado**|**Usar el texto de notificación predeterminado**|**Usar el texto de notificación predeterminado**|No tenemos ninguna recomendación específica para esta configuración. <br/><br/> Puede seleccionar **Usar texto de notificación personalizado** (_CustomNotificationText_) para escribir el texto de notificación personalizado que se va a usar. También puede seleccionar **Usar Traductor de Microsoft** para la localización automática (_UseTranslatedNotificationText_) para traducir el texto de notificación personalizado al idioma del usuario.

## <a name="related-articles"></a>Artículos relacionados

- ¿Está buscando procedimientos recomendados para Exchange de flujo de correo **(también conocidas como reglas de transporte**)? Consulte [Procedimientos recomendados para configurar reglas de flujo de correo en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Los administradores y los usuarios pueden enviar falsos positivos (buen correo electrónico marcado como negativo) y falsos negativos (correo electrónico no permitido) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- Usa estos vínculos para obtener información sobre cómo **configurar el** servicio [EOP](/exchange/standalone-eop/set-up-your-eop-service) y **configurar** [Microsoft Defender para Office 365](defender-for-office-365.md). No olvide las instrucciones útiles en "[Proteger contra amenazas en Office 365](protect-against-threats.md)".

- Las líneas base de seguridad para **Windows** se pueden encontrar aquí: ¿Dónde puedo obtener las líneas base de seguridad [?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para las opciones de GPO/local y Usar líneas base de seguridad para configurar [dispositivos](/intune/protect/security-baselines) Windows en Intune para la seguridad basada en Intune. Por último, una comparación entre Microsoft Defender para punto de conexión y Microsoft Intune de seguridad está disponible en Comparar la Microsoft Defender para punto de conexión [y la Windows Intune  líneas base de seguridad](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
