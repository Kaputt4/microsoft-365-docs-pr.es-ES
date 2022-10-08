---
title: Configuración de ASF en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la configuración del filtro de correo no deseado avanzado (ASF) que están disponibles en las directivas contra correo no deseado en Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 3a4b68d88b63a7c6a572f96fec866d1a4e6ccbff
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68060612"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Configuración del filtro de correo no deseado avanzado (ASF) en EOP

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En todas las organizaciones de Microsoft 365, la configuración del filtro de correo no deseado avanzado (ASF) en las directivas contra correo no deseado de EOP permite a los administradores marcar los mensajes como correo no deseado en función de las propiedades específicas del mensaje. ASF se dirige específicamente a estas propiedades porque se encuentran normalmente en el correo no deseado. Dependiendo de la propiedad, las detecciones de ASF marcarán el mensaje como **spam** o **spam de alta confianza**.

> [!NOTE]
> Habilitar una o varias configuraciones de ASF es un enfoque agresivo para el filtrado de correo no deseado. No se pueden notificar mensajes filtrados por ASF como falsos positivos. Puede identificar los mensajes filtrados por ASF por:
>
> - Notificaciones periódicas de cuarentena de spam y veredictos de filtro de correo no deseado de alta confianza.
> - La presencia de mensajes filtrados en cuarentena.
> - Los campos de encabezado X específicos `X-CustomSpam:` que se agregan a los mensajes, como se describe en este artículo.

En las secciones siguientes se describen las opciones y la configuración de ASF que están disponibles en las directivas contra correo no deseado en el portal de Microsoft 365 Defender y en Exchange Online PowerShell o PowerShell EOP independiente ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) y [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)). Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Habilitación, deshabilitación o prueba de la configuración de ASF

Para cada configuración de ASF, las siguientes opciones están disponibles en las directivas contra correo no deseado:

- **Activado**: ASF agrega el campo de encabezado X correspondiente al mensaje y marca el mensaje como **Spam** (SCL 5 o 6 para [aumentar la configuración de puntuación de correo no deseado](#increase-spam-score-settings)) o **Spam de alta confianza** (SCL 9 para [Marcar como configuración de correo no deseado](#mark-as-spam-settings)).
- **Desactivado**: la configuración de ASF está deshabilitada. Este es el valor predeterminado y se recomienda no cambiarlo.
- **Prueba**: ASF agrega el campo de encabezado X correspondiente al mensaje. Lo que sucede con el mensaje viene determinado por el valor modo **de prueba** (*TestModeAction*):
  - **Ninguno**: la entrega de mensajes no se ve afectada por la detección de ASF. El mensaje sigue estando sujeto a otros tipos de filtrado y reglas en EOP.
  - **Agregar texto de encabezado X predeterminado (*AddXHeader*):** el valor `X-CustomSpam: This message was filtered by the custom spam filter option` de encabezado X se agrega al mensaje. Puede usar este valor en reglas de bandeja de entrada o reglas de flujo de correo (también conocidas como reglas de transporte) para afectar a la entrega del mensaje.
  - **Enviar mensaje de cco (*BccMessage*):** las direcciones de correo electrónico especificadas (el valor del parámetro *TestModeBccToRecipients* en PowerShell) se agregan al campo CCO del mensaje y el mensaje se entrega a los destinatarios de CCO adicionales. En el portal de Microsoft 365 Defender, se separan varias direcciones de correo electrónico por punto y coma (;). En PowerShell, se separan varias direcciones de correo electrónico por comas.

  **Notas**:

  - El modo de prueba no está disponible para la siguiente configuración de ASF:
    - **Filtrado de id. de remitente condicional: error duro** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)
    - **Registro SPF: error duro** (*MarkAsSpamSpfRecordHardFail*)
  - La misma acción de modo de prueba se aplica a *todas las* configuraciones de ASF establecidas en **Prueba**. No puede configurar diferentes acciones de modo de prueba para diferentes opciones de ASF.

## <a name="increase-spam-score-settings"></a>Aumentar la configuración de puntuación de correo no deseado

La siguiente configuración **de ASF Aumentar puntuación de correo no deseado** establece el nivel de confianza de correo no deseado (SCL) de los mensajes detectados en 5 o 6, que corresponde a un veredicto de filtro de **correo no deseado** y a la acción correspondiente en las directivas contra correo no deseado.

|Configuración de directivas contra correo no deseado|Descripción|Encabezado X agregado|
|---|---|---|
|**Vínculos de imagen a sitios web remotos** <p> *IncreaseScoreWithImageLinks*|Los mensajes que contienen `<Img>` vínculos de etiqueta HTML a sitios remotos (por ejemplo, mediante http) se marcan como correo no deseado.|`X-CustomSpam: Image links to remote sites`|
|**Dirección IP numérica en URL** <p> *IncreaseScoreWithNumericIps*|Los mensajes que contienen direcciones URL basadas en números (normalmente, direcciones IP) se marcan como correo no deseado.|`X-CustomSpam: Numeric IP in URL`|
|**Redireccionamiento de direcciones URL a otro puerto** <p> *IncreaseScoreWithRedirectToOtherPort*|El mensaje que contiene hipervínculos que redirigen a puertos TCP distintos de 80 (HTTP), 8080 (HTTP alternativo) o 443 (HTTPS) se marca como correo no deseado.|`X-CustomSpam: URL redirect to other port`|
|**Vínculos a sitios web .biz o .info** <p> *IncreaseScoreWithBizOrInfoUrls*|Los mensajes que contienen `.biz` o `.info` vínculos en el cuerpo del mensaje se marcan como correo no deseado.|`X-CustomSpam: URL to .biz or .info websites`|

## <a name="mark-as-spam-settings"></a>Marcar como configuración de correo no deseado

La siguiente configuración **de Marcar como asf de correo no deseado** establece la SCL de los mensajes detectados en 9, que corresponde a un veredicto de filtro de **correo no deseado de alta confianza** y a la acción correspondiente en las directivas contra correo no deseado.

|Configuración de directivas contra correo no deseado|Descripción|Encabezado X agregado|
|---|---|---|
|**Mensajes vacíos** <p> *MarkAsSpamEmptyMessages*|Los mensajes sin asunto, sin contenido en el cuerpo del mensaje y sin datos adjuntos se marcan como correo no deseado de alta confianza.|`X-CustomSpam: Empty Message`|
|**Etiquetas incrustadas en HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Los mensajes que contienen `<embed>` etiquetas HTML se marcan como correo no deseado de alta confianza. <p> Esta etiqueta permite insertar diferentes tipos de documentos en un documento HTML (por ejemplo, sonidos, vídeos o imágenes).|`X-CustomSpam: Embed tag in html`|
|**JavaScript o VBScript en HTML** <p> *MarkAsSpamJavaScriptInHtml*|Los mensajes que usan JavaScript o Visual Basic Script Edition en HTML se marcan como correo no deseado de alta confianza. <p> Estos lenguajes de scripting se usan en los mensajes de correo electrónico para hacer que se produzcan acciones específicas automáticamente.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Etiquetas Form en HTML** <p> *MarkAsSpamFormTagsInHtml*|Los mensajes que contienen `<form>` etiquetas HTML se marcan como spam de alta confianza. <p> Esta etiqueta se usa para crear formularios de sitio web. Los anuncios en correo electrónico a menudo incluyen esa etiqueta con el fin de solicitar información del destinatario.|`X-CustomSpam: Form tag in html`|
|**Etiquetas de marco o iframe en HTML** <p> *MarkAsSpamFramesInHtml*|Los mensajes que contienen `<frame>` o `<iframe>` etiquetas HTML se marcan como spam de alta confianza. <p> Estas etiquetas se usan en mensajes de correo electrónico para dar formato a la página para mostrar texto o gráficos.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Errores web en HTML** <p> *MarkAsSpamWebBugsInHtml*|Un *error web* (también conocido como *baliza web*) es un elemento gráfico (a menudo tan pequeño como un píxel por un píxel) que se usa en los mensajes de correo electrónico para determinar si el destinatario leyó el mensaje. <p> Los mensajes que contienen errores web se marcan como spam de alta confianza. <p> Los boletines de noticias legítimos pueden usar errores web, aunque muchos consideran esto una invasión de privacidad. |`X-CustomSpam: Web bug`|
|**Etiquetas Object en HTML** <p> *MarkAsSpamObjectTagsInHtml*|Los mensajes que contienen `<object>` etiquetas HTML se marcan como spam de alta confianza. <p> Esta etiqueta permite que los complementos o aplicaciones se ejecuten en una ventana HTML.|`X-CustomSpam: Object tag in html`|
|**Palabras confidenciales** <p> *MarkAsSpamSensitiveWordList*|Microsoft mantiene una lista dinámica pero no modificable de palabras asociadas a mensajes potencialmente ofensivos. <p> Los mensajes que contienen palabras de la lista de palabras confidenciales en el asunto o el cuerpo del mensaje se marcan como correo no deseado de alta confianza.|`X-CustomSpam: Sensitive word in subject/body`|
|**Registro de SPF: error** <p> *MarkAsSpamSpfRecordHardFail*|Los mensajes enviados desde una dirección IP que no se especifica en el registro SPF Sender Policy Framework (SPF) en DNS para el dominio de correo electrónico de origen se marcan como correo no deseado de alta confianza. <p> El modo de prueba no está disponible para esta configuración.|`X-CustomSpam: SPF Record Fail`|

La siguiente configuración **de Marcar como ASF de correo no deseado** establece la SCL de los mensajes detectados en 6, que corresponde a un veredicto de filtro **de correo no deseado** y a la acción correspondiente en las directivas contra correo no deseado.

|Configuración de directivas contra correo no deseado|Descripción|Encabezado X agregado|
|---|---|---|
|**Error de filtrado de identificador de remitente** <p> *MarkAsSpamFromAddressAuthFail*|Los mensajes que no cumplen una comprobación condicional del identificador de remitente se marcan como correo no deseado. <p> Esta configuración combina una comprobación de SPF con una comprobación de id. de remitente para ayudar a protegerse frente a encabezados de mensaje que contienen remitentes falsificados. <p> El modo de prueba no está disponible para esta configuración.|`X-CustomSpam: SPF From Record Fail`|
|**Retrodispersión** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* es informes de no entrega inútiles (también conocidos como NDR o mensajes de rebote) causados por remitentes falsificados en mensajes de correo electrónico. Para obtener más información, vea [Mensajes backscatter y EOP](backscatter-messages-and-eop.md). <p> No es necesario configurar esta configuración en los siguientes entornos, ya que se entregan NDR legítimos y backscatter está marcado como spam: <ul><li>Organizaciones de Microsoft 365 con buzones de Exchange Online.</li><li>Organizaciones de correo electrónico locales donde se enruta correo electrónico *saliente* a través de EOP.</li></ul> <p> En entornos EOP independientes que protegen el correo electrónico entrante en buzones locales, activar o desactivar esta configuración tiene el siguiente resultado: <ul><li> **Activado**: Se entregan los NDR legítimos y el backscatter se marca como spam.</li><li>**Desactivado**: los NDR legítimos y backscatter pasan por el filtrado normal de correo no deseado. La mayoría de los NDR legítimos se entregarán al remitente del mensaje original. Algunos, pero no todos, se marcan como spam. Por definición, el backscatter solo se puede entregar al remitente suplantado, no al remitente original.</li></ul> <p> El modo de prueba no está disponible para esta configuración.|`X-CustomSpam: Backscatter NDR`|
