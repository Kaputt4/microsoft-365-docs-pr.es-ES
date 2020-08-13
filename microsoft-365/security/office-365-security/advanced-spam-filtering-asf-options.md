---
title: Configuración de ASF en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la configuración de filtro de correo no deseado avanzada (ASF) que está disponible en las directivas contra correo no deseado en Exchange Online Protection (EOP).
ms.openlocfilehash: b314b8b2a2de72987d9acff688602df0e0947293
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653346"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Configuración de filtro de correo no deseado avanzado (ASF) en EOP

> [!NOTE]
> La configuración de ASF que está disponible actualmente en las directivas contra correo no deseado está en desuso. Le recomendamos que no use estas opciones en las directivas contra correo no deseado. La funcionalidad de esta configuración ASF se incorpora a otras partes de la pila de filtrado. Para obtener más información, vea [configuración de la Directiva contra correo no deseado de EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, la configuración de filtro de correo no deseado (ASF) en las directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o de filtrado ASF se destina específicamente a estas propiedades porque suelen encontrarse en el correo no deseado. En función de la propiedad, las detecciones ASF marcarán el mensaje como **correo no deseado** o **correo no deseado de alta confianza**.

> [!NOTE]
> La habilitación de una o varias opciones de ASF es un enfoque agresivo del filtrado de correo no deseado. No puede informar de mensajes filtrados por ASF como falsos positivos. Puede identificar mensajes filtrados por ASF:
> - Notificaciones de cuarentena de correo no deseado para el usuario final periódico.
>
> - La presencia de mensajes filtrados en cuarentena.
>
> - Los `X-CustomSpam:` campos de encabezado X específicos que se agregan a los mensajes, tal y como se describe en este tema.

En las siguientes secciones se describe la configuración y las opciones de ASF que están disponibles en las directivas contra correo no deseado en el centro de seguridad & cumplimiento y en Exchange Online PowerShell o en Windows EOP independiente ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) y [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)). Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Habilitar, deshabilitar o probar la configuración de ASF

Para cada configuración ASF, las siguientes opciones están disponibles en las directivas contra correo no deseado:

- **On**: ASF agrega el campo de encabezado X correspondiente al mensaje y marca el mensaje como **correo no deseado** (SCL 5 o 6 para [aumentar la configuración de puntuación de correo no deseado](#increase-spam-score-settings)) o **correo no deseado de alta confianza** (SCL 9 para [marcarlo como correo no deseado](#mark-as-spam-settings)).

- **Desactivado**: la configuración ASF está deshabilitada. Este es el valor predeterminado y le recomendamos que no lo cambie.

- **Test**: ASF agrega el campo de encabezado X correspondiente al mensaje. El valor de **las opciones del modo de prueba** (*TestModeAction*) determina lo que ocurre con el mensaje:

  - **Ninguno**: el enrutamiento y la entrega de mensajes no se ven afectados por la detección de ASF. El mensaje sigue sujeto a otros tipos de filtrado y reglas en EOP.

  - **Agregar texto de encabezado x predeterminado (*AddXHeader*)**: el valor del encabezado x `X-CustomSpam: This message was filtered by the custom spam filter option` se agrega al mensaje. Puede usar este valor en reglas de la bandeja de entrada o en reglas de flujo de correo (también conocidas como reglas de transporte) para afectar a la distribución y la entrega del mensaje.

  - **Enviar mensaje CCO (*BccMessage*)**: las direcciones de correo electrónico especificadas (el valor del parámetro *TestModeBccToRecipients* en PowerShell) se agregan al campo BCC del mensaje y el mensaje se entrega a los destinatarios CCO. En el centro de seguridad & cumplimiento, separe varias direcciones de correo electrónico con punto y coma (;). En PowerShell, se separan varias direcciones de correo electrónico por comas.

  **Notas**:

  - El modo de prueba no está disponible para los siguientes valores de ASF:

    - **Filtrado de identificador de remitente condicional: error grave** (*MarkAsSpamFromAddressAuthFail*)
    - **Retrodispersión de NDR**(*MarkAsSpamNdrBackscatter*)
    - **Registro de SPF: error grave** (*MarkAsSpamSpfRecordHardFail*)

  - Se aplica la misma acción de modo de prueba a *todos los* valores de ASF establecidos para la **prueba**. No se pueden configurar distintas acciones del modo de prueba para la configuración de ASF diferente.

## <a name="increase-spam-score-settings"></a>Aumentar la configuración de la puntuación de correo no deseado

La siguiente configuración ASF establece el nivel de confianza contra correo no deseado (SCL) de los mensajes detectados en 5 o 6, que corresponde al veredicto del filtro de **correo no deseado** y a la acción correspondiente en las directivas contra correo no deseado.

****

|Configuración de la Directiva contra correo no deseado|Description|Encabezado X agregado|
|---|---|---|
|**Vínculos de imagen a sitios remotos** <br/><br/> *IncreaseScoreWithImageLinks*|Los mensajes que contienen `<Img>` vínculos de etiquetas HTML a sitios remotos (por ejemplo, mediante http) se marcan como correo no deseado.|`X-CustomSpam: Image links to remote sites`|
|**Redireccionamiento de direcciones URL a otro puerto** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|Los mensajes que contienen hipervínculos que se redirigen a puertos TCP distintos de 80 (HTTP), 8080 (HTTP alternativo) o 443 (HTTPS) se marcan como correo no deseado.|`X-CustomSpam: URL redirect to other port`|
|**Dirección IP numérica en URL** <br/><br/> *IncreaseScoreWithNumericIps*|Los mensajes que contienen direcciones URL basadas en números (normalmente, direcciones IP) se marcan como correo no deseado.|`X-CustomSpam: Numeric IP in URL`|
|**Dirección URL de sitios web .biz o .info** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|Los mensajes que contienen vínculos. BIZ o. info en el cuerpo del mensaje se marcan como correo no deseado.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Marcar como configuración de correo no deseado

La siguiente configuración ASF establece el SCL de los mensajes detectados en 9, que corresponde al filtro de **correo no deseado de confianza alta** y a la acción correspondiente en las directivas contra correo no deseado.

****

|Configuración de la Directiva contra correo no deseado|Description|Encabezado X agregado|
|---|---|---|
|**Mensajes vacíos** <br/><br/> *MarkAsSpamEmptyMessages*|Los mensajes sin asunto, sin contenido en el cuerpo del mensaje y sin datos adjuntos, no se marcan como correo no deseado de confianza alta.|`X-CustomSpam: Empty Message`|
|**JavaScript o VBScript en HTML** <br/><br/> *MarkAsSpamJavaScriptInHtml*|Los mensajes que utilizan JavaScript o Visual Basic Script Edition en HTML están marcados como correo no deseado de alta confianza. <br/><br/> Estos lenguajes de scripting se usan en los mensajes de correo electrónico para que se produzcan acciones específicas automáticamente.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Etiquetas Frame o IFrame en HTML** <br><br/> *MarkAsSpamFramesInHtml*|Los mensajes que contienen `<frame>` o `<iframe>` etiquetas HTML están marcados como correo no deseado de confianza alta. <br/><br/> Estas etiquetas se usan en los mensajes de correo electrónico para dar formato a la página para mostrar texto o gráficos.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Etiquetas Object en HTML** <br><br/> *MarkAsSpamObjectTagsInHtml*|Los mensajes que contienen `<object>` etiquetas HTML se marcan como correo no deseado de confianza alta. <br/><br/> Esta etiqueta permite ejecutar complementos o aplicaciones en una ventana HTML.|`X-CustomSpam: Object tag in html`|
|**Etiquetas Embed en HTML** <br><br/> *MarkAsSpamEmbedTagsInHtml*|Los mensajes que contienen `<embed>` etiquetas HTML están marcados como correo no deseado de confianza alta. <br/><br/> Esta etiqueta permite la incrustación de distintos tipos de documentos de distintos tipos de datos en un documento HTML (por ejemplo, sonidos, películas o imágenes).|`X-CustomSpam: Embed tag in html`|
|**Etiquetas Form en HTML** <br><br/> *MarkAsSpamFormTagsInHtml*|Los mensajes que contienen `<form>` etiquetas HTML se marcan como correo no deseado de confianza alta. <br/><br/> Esta etiqueta se usa para crear formularios de sitios Web. Los anuncios en correo electrónico a menudo incluyen esa etiqueta con el fin de solicitar información del destinatario.|`X-CustomSpam: Form tag in html`|
|**Errores web en HTML** <br><br/> *MarkAsSpamWebBugsInHtml*|Un *Web Bug* (también conocido como *baliza web*) es un elemento gráfico (a menudo con un tamaño de un píxel en un píxel) que se usa en los mensajes de correo electrónico para determinar si se leyó el mensaje. <br/><br/> Los mensajes que contienen Web bugs están marcados como correo no deseado de confianza alta. <br/><br/> Los boletines legítimos podrían usar bugs Web, aunque muchos consideran la invasión de la privacidad. |`X-CustomSpam: Web bug`|
|**Aplicar lista de palabras confidenciales** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft mantiene una lista de palabras dinámicas pero no editables que están asociadas a mensajes potencialmente ofensivos. <br/><br/> Los mensajes que contienen palabras de la lista de palabras confidenciales en el asunto o el cuerpo del mensaje están marcados como correo no deseado de alta confianza.|`X-CustomSpam: Sensitive word in subject/body`|
|**Registro de SPF: error** <br><br/> *MarkAsSpamSpfRecordHardFail*|Los mensajes enviados desde una dirección IP que no se especifica en el registro de marco de directivas de remitente (SPF) de SPF en DNS para el dominio de correo electrónico de origen se marcan como correo no deseado de confianza alta. <br/><br/> El modo de prueba no está disponible para esta opción.|`X-CustomSpam: SPF Record Fail`|
|**Filtrado de identificador del remitente condicional: error** <br><br/> *MarkAsSpamFromAddressAuthFail*|Mensajes que un error grave se marca una comprobación de identificador de remitente condicional como correo no deseado. <br/><br/> Esta opción combina una comprobación SPF con una comprobación del identificador de remitente para ayudar a protegerse contra los encabezados de mensaje que contienen remitentes falsificados. <br/><br/> El modo de prueba no está disponible para esta opción.|`X-CustomSpam: SPF From Record Fail`|
|**Reenvío masivo de correo electrónico no deseado de NDR** <br><br/> *MarkAsSpamNdrBackscatter*|La *indispersión* es inútil los informes de no entrega (también conocidos como NDR o mensajes de devolución) causados por los remitentes falsificados en mensajes de correo electrónico. Para obtener más información, vea [mensajes de reenvío masivo y EOP](backscatter-messages-and-eop.md). <br/><br/> No es necesario configurar esta opción en los siguientes entornos, ya que se entregan NDR legítimos y la dispersión se marca como correo no deseado: <ul><li>Microsoft 365 organizaciones con buzones de correo de Exchange Online.</li><li>Organizaciones de correo electrónico locales donde enrutar el correo electrónico *saliente* a través de EOP.</li></ul><br/> En entornos de EOP independientes que protegen el correo electrónico entrante a los buzones locales, activar o desactivar esta configuración tiene el siguiente resultado: <ul><li> **On**: se entregan NDR legítimos y la dispersión se marca como correo no deseado.</li><li>**Desactivado**: los NDR legítimos y el indispersión pasan por el filtrado de correo no deseado normal. La mayoría de los NDR legítimos se entregarán al remitente del mensaje original. Algunas, pero no todas, la dispersión se marcan como correo no deseado de confianza alta. Por definición, la función de multidifusión solo se puede entregar al remitente suplantado, no al remitente original.</li></ul><br/> El modo de prueba no está disponible para esta opción.|`X-CustomSpam: Backscatter NDR`|
|
