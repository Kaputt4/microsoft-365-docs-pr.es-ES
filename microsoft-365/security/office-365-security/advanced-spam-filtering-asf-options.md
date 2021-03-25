---
title: Configuración de ASF en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la configuración del filtro de correo no deseado avanzado (ASF) que están disponibles en las directivas contra correo no deseado en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ade36086d1503b89b506730b98ac7965845e86b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207454"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Configuración avanzada del filtro de correo no deseado (ASF) en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> La configuración de ASF que está disponible actualmente en las directivas contra correo no deseado está en desuso. Se recomienda no usar esta configuración en directivas contra correo no deseado. La funcionalidad de esta configuración de ASF se está incorporando a otras partes de la pila de filtrado. Para obtener más información, vea [Configuración de la directiva contra correo no deseado de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

En todas las organizaciones de Microsoft 365, la configuración del Filtro de correo no deseado avanzado (ASF) en las directivas contra correo no deseado en EOP permite a los administradores marcar los mensajes como correo no deseado en función de propiedades de mensaje específicas. ASF se dirige específicamente a estas propiedades porque se encuentran comúnmente en correo no deseado. Según la propiedad, las detecciones de ASF marcarán el mensaje como **Correo** no deseado o Correo no **deseado de alta confianza.**

> [!NOTE]
> Habilitar una o varias opciones de configuración de ASF es un enfoque agresivo para el filtrado de correo no deseado. No puede notificar mensajes filtrados por ASF como falsos positivos. Puede identificar los mensajes filtrados por ASF mediante:
>
> - Notificaciones periódicas de cuarentena de correo no deseado del usuario final.
>
> - La presencia de mensajes filtrados en cuarentena.
>
> - Los campos `X-CustomSpam:` de encabezado X específicos que se agregan a los mensajes como se describe en este artículo.

En las secciones siguientes se describen las opciones y la configuración de ASF que están disponibles en las directivas contra correo no deseado en el Centro de seguridad y cumplimiento de & y en PowerShell de Exchange Online o en PowerShell de EOP independiente ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) y [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)). Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Habilitar, deshabilitar o probar la configuración de ASF

Para cada configuración de ASF, las siguientes opciones están disponibles en las directivas contra correo no deseado:

- **On**: ASF agrega el campo de encabezado X correspondiente al mensaje y marca el mensaje como **Correo** no deseado (SCL 5 o 6 para Aumentar la configuración de puntuación de **correo** no [deseado)](#increase-spam-score-settings)o Correo no deseado de confianza alta (SCL 9 para [Marcar](#mark-as-spam-settings)como configuración de correo no deseado).

- **Desactivado:** la configuración de ASF está deshabilitada. Este es el valor predeterminado y le recomendamos que no lo cambie.

- **Prueba:** ASF agrega el campo de encabezado X correspondiente al mensaje. Lo que sucede con el mensaje viene determinado por el **valor De las** opciones del modo de prueba (*TestModeAction*):

  - **Ninguno:** la entrega de mensajes no se ven afectadas por la detección de ASF. El mensaje todavía está sujeto a otros tipos de filtrado y reglas en EOP.

  - **Agregar texto de encabezado X predeterminado (*AddXHeader*):** El valor de encabezado X `X-CustomSpam: This message was filtered by the custom spam filter option` se agrega al mensaje. Puede usar este valor en reglas de bandeja de entrada o reglas de flujo de correo (también conocidas como reglas de transporte) para afectar a la entrega del mensaje.

  - **Enviar mensaje CCO (*BccMessage*):** las direcciones de correo electrónico especificadas (el valor del parámetro *TestModeBccToRecipients* en PowerShell) se agregan al campo CCO del mensaje y el mensaje se entrega a los destinatarios CCO adicionales. En el Centro de & seguridad, se separan varias direcciones de correo electrónico por punto y coma (;). En PowerShell, se separan varias direcciones de correo electrónico por comas.

  **Notas**:

  - El modo de prueba no está disponible para la siguiente configuración de ASF:

    - **Filtrado de id. de remitente condicional: error** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)
    - **Registro SPF: error duro** (*MarkAsSpamSpfRecordHardFail*)

  - La misma acción de modo de prueba se aplica a *todas las* configuraciones de ASF que se establecen en **Probar**. No puede configurar distintas acciones de modo de prueba para distintas configuraciones de ASF.

## <a name="increase-spam-score-settings"></a>Aumentar la configuración de puntuación de correo no deseado

La siguiente configuración de ASF establece el nivel de confianza de correo no deseado  (SCL) de los mensajes detectados en 5 o 6, que corresponde al veredicto de filtro de correo no deseado y a la acción correspondiente en las directivas contra correo no deseado.

****

|Configuración de directiva contra correo no deseado|Descripción|Encabezado X agregado|
|---|---|---|
|**Vínculos de imagen a sitios remotos** <p> *IncreaseScoreWithImageLinks*|Los mensajes que contienen vínculos de etiqueta HTML a sitios remotos `<Img>` (por ejemplo, mediante http) se marcan como correo no deseado.|`X-CustomSpam: Image links to remote sites`|
|**Redireccionamiento de direcciones URL a otro puerto** <p> *IncreaseScoreWithRedirectToOtherPort*|Los mensajes que contienen hipervínculos que redirigen a puertos TCP distintos de 80 (HTTP), 8080 (HTTP alternativo) o 443 (HTTPS) se marcan como correo no deseado.|`X-CustomSpam: URL redirect to other port`|
|**Dirección IP numérica en URL** <p> *IncreaseScoreWithNumericIps*|Los mensajes que contienen direcciones URL basadas en números (normalmente, direcciones IP) se marcan como correo no deseado.|`X-CustomSpam: Numeric IP in URL`|
|**Dirección URL de sitios web .biz o .info** <p> *IncreaseScoreWithBizOrInfoUrls*|Los mensajes que contienen `.biz` `.info` o vínculos en el cuerpo del mensaje se marcan como correo no deseado.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Marcar como configuración de correo no deseado

La siguiente configuración de ASF establece el SCL de los mensajes detectados en 9, que corresponde al veredicto de filtro de **correo no** deseado de elevada confianza y a la acción correspondiente en las directivas contra correo no deseado.

****

|Configuración de directiva contra correo no deseado|Descripción|Encabezado X agregado|
|---|---|---|
|**Mensajes vacíos** <p> *MarkAsSpamEmptyMessages*|Los mensajes sin asunto, sin contenido en el cuerpo del mensaje y sin datos adjuntos se marcan como correo no deseado de elevada confianza.|`X-CustomSpam: Empty Message`|
|**JavaScript o VBScript en HTML** <p> *MarkAsSpamJavaScriptInHtml*|Los mensajes que usan JavaScript o Visual Basic Script Edition en HTML se marcan como correo no deseado de elevada confianza. <p> Estos lenguajes de scripting se usan en los mensajes de correo electrónico para hacer que se produzcan acciones específicas automáticamente.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Etiquetas Frame o IFrame en HTML** <p> *MarkAsSpamFramesInHtml*|Los mensajes que contienen o etiquetas HTML se marcan como correo no deseado `<frame>` `<iframe>` de elevada confianza. <p> Estas etiquetas se usan en mensajes de correo electrónico para dar formato a la página para mostrar texto o gráficos.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Etiquetas Object en HTML** <p> *MarkAsSpamObjectTagsInHtml*|Los mensajes que contienen `<object>` etiquetas HTML se marcan como correo no deseado de elevada confianza. <p> Esta etiqueta permite que los complementos o aplicaciones se ejecuten en una ventana HTML.|`X-CustomSpam: Object tag in html`|
|**Etiquetas Embed en HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Los mensajes que contienen `<embed>` etiquetas HTML se marcan como correo no deseado de elevada confianza. <p> Esta etiqueta permite insertar diferentes tipos de documentos en un documento HTML (por ejemplo, sonidos, vídeos o imágenes).|`X-CustomSpam: Embed tag in html`|
|**Etiquetas Form en HTML** <p> *MarkAsSpamFormTagsInHtml*|Los mensajes que contienen `<form>` etiquetas HTML se marcan como correo no deseado de elevada confianza. <p> Esta etiqueta se usa para crear formularios de sitio web. Los anuncios en correo electrónico a menudo incluyen esa etiqueta con el fin de solicitar información del destinatario.|`X-CustomSpam: Form tag in html`|
|**Errores web en HTML** <p> *MarkAsSpamWebBugsInHtml*|Un *error web* (también conocido como baliza *web)* es un elemento gráfico (a menudo tan pequeño como un píxel por un píxel) que se usa en los mensajes de correo electrónico para determinar si el destinatario leyó el mensaje. <p> Los mensajes que contienen errores web se marcan como correo no deseado de elevada confianza. <p> Los boletines legítimos pueden usar errores web, aunque muchos consideran que esto es una invasión de la privacidad. |`X-CustomSpam: Web bug`|
|**Aplicar lista de palabras confidenciales** <p> *MarkAsSpamSensitiveWordList*|Microsoft mantiene una lista dinámica pero no editable de palabras asociadas con mensajes potencialmente ofensivos. <p> Los mensajes que contienen palabras de la lista de palabras confidenciales del asunto o cuerpo del mensaje se marcan como correo no deseado de elevada confianza.|`X-CustomSpam: Sensitive word in subject/body`|
|**Registro de SPF: error** <p> *MarkAsSpamSpfRecordHardFail*|Los mensajes enviados desde una dirección IP que no se especifica en el registro SPF Sender Policy Framework (SPF) en DNS para el dominio de correo electrónico de origen se marcan como correo no deseado de elevada confianza. <p> El modo de prueba no está disponible para esta configuración.|`X-CustomSpam: SPF Record Fail`|
|**Filtrado de identificador del remitente condicional: error** <p> *MarkAsSpamFromAddressAuthFail*|Los mensajes que no cumplen una comprobación condicional del id. del remitente se marcan como correo no deseado. <p> Esta configuración combina una comprobación de SPF con una comprobación de id. de remitente para ayudar a proteger contra encabezados de mensaje que contienen remitentes falsificados. <p> El modo de prueba no está disponible para esta configuración.|`X-CustomSpam: SPF From Record Fail`|
|**Reenvío masivo de correo electrónico no deseado de NDR** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* es informes de no entrega inútiles (también conocidos como NDR o mensajes de despegar) causados por remitentes falsificados en mensajes de correo electrónico. Para obtener más información, [vea Backscatter messages y EOP](backscatter-messages-and-eop.md). <p> No es necesario configurar esta configuración en los siguientes entornos, ya que se entregan NDR legítimos y el backscatter se marca como correo no deseado: <ul><li>Organizaciones de Microsoft 365 con buzones de Exchange Online.</li><li>Organizaciones de correo electrónico locales a las que se *enruta el correo* electrónico saliente a través de EOP.</li></ul> <p> En entornos EOP independientes que protegen el correo electrónico entrante en buzones locales, activar o desactivar esta configuración tiene el siguiente resultado: <ul><li> **On**: Se entregan NDR legítimos y el backscatter se marca como correo no deseado.</li><li>**Desactivado:** los NDR legítimos y el backscatter pasan por el filtrado de correo no deseado normal. La mayoría de las NDR legítimas se entregarán al remitente del mensaje original. Algunos, pero no todos, se marcan como correo no deseado de elevada confianza. Por definición, el backscatter solo se puede entregar al remitente suplantado, no al remitente original.</li></ul> <p> El modo de prueba no está disponible para esta configuración.|`X-CustomSpam: Backscatter NDR`|
|