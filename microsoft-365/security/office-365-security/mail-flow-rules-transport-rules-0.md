---
title: Reglas de flujo de correo en EOP
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
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: Puede usar reglas de flujo de correo (reglas de transporte) para identificar y realizar acciones en mensajes que fluyen a través de la organización.
ms.openlocfilehash: 8eb4b805065ef1e279c5bbdab17a86b29aacc17b
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209696"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>Reglas de flujo de correo (reglas de transporte) en EOP independiente

En las organizaciones independientes de Exchange Online Protection (EOP) que no tienen buzones de Exchange Online, puede usar reglas de flujo de correo (también conocidas como reglas de transporte) para identificar y realizar acciones en los mensajes que fluyen por la organización.

En este tema se explican los componentes de las reglas de flujo de correo y cómo funcionan.

Para conocer los pasos para crear, copiar y administrar reglas de flujo de correo, consulte [Manage mail Flow Rules in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). Para cada regla, tiene la posibilidad de aplicarla, probarla o probarla y notificar al remitente. Para obtener más información sobre las opciones de prueba, consulte [probar reglas de flujo de correo](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) y [sugerencias de directivas en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips).

Para obtener informes de resumen e informes detallados sobre los mensajes que coinciden con las reglas de flujo de correo, consulte [usar informes de protección de correo para ver datos sobre malware, correo no deseado y detecciones de reglas](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).

Para implementar directivas de mensajería específicas mediante el uso de reglas de flujo de correo, vea estos temas:

- [Usar reglas de flujo de correo para inspeccionar datos adjuntos de mensajes en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Configurar el cifrado en Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Avisos de declinación de responsabilidad de mensajes, firmas, pies de página o encabezados en toda la organización en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Use reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md)

- [Reducción de las amenazas de malware a través del bloqueo de datos adjuntos en Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definir reglas para cifrar o descifrar mensajes de correo electrónico en Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

En el vídeo siguiente se ofrece una demostración de la configuración de reglas de flujo de correo en EOP independiente.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Componentes de las reglas de flujo de correo

Una regla de flujo de correo consta de condiciones, excepciones, acciones y propiedades:

- **Condiciones**: Identifique los mensajes a los que desea aplicar las acciones. Algunas condiciones examinan campos de encabezado del mensaje (por ejemplo, los campos Para, De o CC). Otras examinan propiedades del mensaje (por ejemplo, el asunto, el cuerpo, los datos adjuntos, el tamaño del mensaje o la clasificación del mensaje). La mayoría de las condiciones exigen que se especifique un operador de comparación (por ejemplo, es igual a, no es igual a o contiene) y un valor de coincidencia. En caso de que no haya condiciones o excepciones, la regla se aplica a todos los mensajes.

Para obtener más información acerca de las condiciones de las reglas de flujo de correo en EOP independiente, consulte [mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Excepciones**: opcionalmente, identifique los mensajes a los que no se deben aplicar las acciones. Los mismos identificadores de mensaje que están disponibles en las condiciones están también disponibles en las excepciones. Las excepciones invalidan las condiciones e impiden que se apliquen las acciones de regla a un mensaje, aunque este cumpla todas las condiciones configuradas.

- **Acciones**: especificar qué hacer a los mensajes que coinciden con las condiciones de la regla y que no coinciden con ninguna de las excepciones. Existen numerosas acciones disponibles, como, por ejemplo, rechazar, eliminar o redirigir mensajes; agregar más destinatarios; agregar prefijos al asunto del mensaje; o insertar avisos de declinación de responsabilidades en el cuerpo del mensaje.

Para obtener más información sobre las acciones de las reglas de flujo de correo que están disponibles en EOP independiente, consulte [mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Propiedades**: especifique otras configuraciones de reglas que no sean condiciones, excepciones o acciones. Por ejemplo, especifican cuándo debe aplicarse la regla, si se va a aplicar o a probar y el periodo de tiempo en el que está activa.

  Para obtener más información, consulte la sección [Propiedades de las reglas de flujo de correo](#mail-flow-rule-properties) de este tema.

### <a name="multiple-conditions-exceptions-and-actions"></a>Múltiples condiciones, excepciones y acciones

En la siguiente tabla se muestra cómo se controlan múltiples condiciones, valores de condición, excepciones y acciones en una regla.

|**Componente**|**Lógica**|**Comments**|
|:-----|:-----|:-----|
|Comentarios|Y|Un mensaje debe cumplir todas las condiciones de la regla. Si tiene que cumplir una condición u otra, use reglas independientes para cada condición. Por ejemplo, si desea agregar el mismo aviso de declinación de responsabilidades a los mensajes con archivos adjuntos y a los mensajes que contienen un texto específico, cree una regla para cada condición. En el EAC, puede copiar fácilmente una regla.|
|Un mensaje debe coincidir con todas las condiciones de la regla. Si necesita alternar la coincidencia entre una condición y otra, use reglas independientes para cada condición. Por ejemplo, si desea agregar la misma declinación de responsabilidad a los mensajes con archivos adjuntos y a los mensajes cuyo contenido coincide con un patrón, cree una regla para cada condición. Puede copiar fácilmente una regla.|O|Determinadas condiciones permiten especificar más de un valor. El mensaje debe coincidir con alguno de los valores especificados (no todos). Por ejemplo, si un mensaje de correo tiene el asunto Información del precio en bolsa y la condición **El asunto incluye cualquiera de estas palabras** está establecida para coincidir con las palabras Contoso o bolsa, la condición se cumple ya que el asunto contiene al menos uno de los valores de la condición.  |
|Determinadas condiciones permiten especificar más de un valor. Si una condición permite indicar múltiples valores, el mensaje debe coincidir con alguno de los valores especificados en dicha condición. Por ejemplo, si un mensaje de correo electrónico tiene el asunto Información del precio en bolsa y la condición El asunto incluye cualquiera de estas palabras está establecida para coincidir con las palabras Contoso o bolsa, la condición se cumple ya que el asunto contiene al menos uno de los valores de la condición.|O|Si un mensaje coincide con alguna de las excepciones, las acciones no se aplican al mensaje. El mensaje no tiene que coincidir con todas las excepciones.|
|Si un mensaje coincide con alguna de las excepciones, no se procesan las acciones. El mensaje no tiene que coincidir con todas las excepciones.|Y|Mensajes que coinciden con las condiciones de una regla obtienen todas las acciones que se especifican en la regla. Por ejemplo, si se seleccionan las acciones **Anteponer al asunto del mensaje** y **Agregar destinatarios en el cuadro CCO**, ambas acciones se aplican al mensaje.  <br/><br/> Los mensajes que coinciden con las condiciones de una regla son objeto de todas las acciones especificadas en dicha regla. Por ejemplo, si las acciones Anteponer el asunto del mensaje con y Agregar destinatarios al cuadro Enviar copia oculta están seleccionadas, ambas se aplican al mensaje. La cadena especificada se antepondrá al asunto del mensaje y los remitentes especificados se añadirán como recipientes Cco.<br/><br/> También puede establecer una acción en una regla de modo que cuando se aplique la regla, no se apliquen las reglas posteriores al mensaje.|

### <a name="mail-flow-rule-properties"></a>Propiedades de las reglas de flujo de correo

En la tabla siguiente se describen las propiedades de regla que están disponibles en las reglas de flujo de correo.

|**Nombre de la propiedad en el EAC**|**Nombre del parámetro en PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|**Prioridad**|_Priority_|Indica el orden en el que se aplican las reglas a los mensajes. La prioridad predeterminada se establece en función del momento en el que se creó la regla (las reglas más antiguas tienen más prioridad que las más recientes y las reglas con una prioridad superior se procesan antes que las que tienen una prioridad inferior).   <br/><br/> La prioridad de la regla en el EAC se cambia moviendo la regla hacia arriba o hacia abajo en la lista de reglas. En PowerShell, establezca el número de prioridad (0 es la prioridad más alta). <br/><br/> Por ejemplo, si dispone de una regla para rechazar mensajes que incluyan un número de tarjeta de crédito y otra que exija su probación, deseará que se aplique primero la regla de rechazo y que dejen de aplicarse las demás.  |
|**Modo**|_Mode_|Puede especificar si quiere que la regla inicie el procesamiento de mensajes inmediatamente o si quiere probar las reglas sin afectar a la entrega del mensaje (con o sin sugerencias de directiva de prevención de pérdida de datos o DLP). <br/><br/> Mediante las sugerencias de directiva, se muestra una nota breve en Outlook o en Outlook en la web que ofrece información sobre posibles infracciones de la directiva al usuario que crea el mensaje. Para obtener más información, consulte **Policy Tips**.  <br/><br/> Para obtener más información acerca de los modos, consulte **Test a mail flow rule**.|
|**Activar esta regla en la siguiente fecha** <br/><br/> **Desactivar esta regla en la siguiente fecha**|_ActivationDate_ <br/> _ExpiryDate_|Especifica el intervalo de fechas en que la regla está activa.|
|Casilla **Activado** seleccionada o no|New rules: _Enabled_ parámetro en el cmdlet **New-TransportRule** . <br/><br/> Reglas existentes: Usar los cmdlets **Enable-TransportRule** o **Disable-TransportRule**. <br/><br/> El valor se muestra en la propiedad **State** de la regla.|Puede crear una regla deshabilitada y habilitarla cuando desee probarla. O bien, puede deshabilitar una regla sin eliminarla para conservar la configuración.|
|**Aplazar el mensaje si no se completa el procesamiento de la regla**|_RuleErrorAction_|Puede especificar cómo debe tratarse el mensaje si el procesamiento de la regla no se puede completar. La regla se omitirá de forma predeterminada, pero el mensaje se puede volver a enviar para su procesamiento.|
|**La dirección del remitente debe coincidir con el siguiente elemento del mensaje**|_SenderAddressLocation_|Si la regla usa condiciones o excepciones que examinan la dirección de correo electrónico del remitente, puede buscar el valor en el encabezado del mensaje, en el sobre del mensaje o en ambos.|
|**Detener el procesamiento de más reglas**|_SenderAddressLocation_|Se trata de una acción para la regla, pero parece una propiedad en el EAC. Puede dejar de aplicar reglas adicionales a un mensaje después de que esta regla procese un mensaje.|
|**Comentarios**|_Comments_|Puede escribir comentarios descriptivos sobre la regla.|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Cómo se aplican las reglas de flujo de correo a los mensajes

Todo el flujo de mensajes de su organización se evalúa mediante las reglas de flujo de correo habilitadas en esta. Las reglas se procesan en el orden que **Mail flow** aparecen en la \> página **reglas** de flujo de correo en EAC, o bien en función del valor de parámetro _Priority_ correspondiente en PowerShell.

Cada regla también ofrece la opción de detener el procesamiento de reglas adicionales si se encuentra una coincidencia con la regla en cuestión. Esta configuración es importante para los mensajes que coinciden con las condiciones de varias reglas de flujo de correo (¿qué regla desea que se aplique al mensaje? ¿Todas? ¿Solo una?).

### <a name="differences-in-processing-based-on-message-type"></a>Diferencias en el procesamiento según el tipo de mensaje

Hay varios tipos de mensajes que pasan a través de una organización. En la tabla siguiente, se muestran los tipos de mensajes que se pueden procesar mediante reglas de flujo de correo.

|**Tipo de mensaje**|**¿Se puede aplicar una regla?**|
|:-----|:-----|
|**Mensajes normales**: mensajes que contienen un único formato de texto enriquecido (RTF), HTML, un cuerpo de mensaje de texto sin formato o un conjunto alternativo o de varias partes de cuerpos de mensaje.|Sí|
|**Office 365 cifrado de mensajes**: mensajes cifrados por el cifrado de mensajes de Office 365 en Office 365. Para obtener más información, vea [Cifrado en Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).|Las reglas siempre pueden acceder a los encabezados de sobre y procesar los mensajes según las condiciones que se inspeccionan en los encabezados. <br/><br/> Para que una regla inspeccione o modifique el contenido de un mensaje cifrado, deberá comprobar que el descifrado de transporte está habilitado (como obligatorio u opcional; el valor predeterminado es Opcional). Para obtener más información, vea [definir reglas para cifrar o descifrar mensajes de correo electrónico en Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).|
|**Mensajes cifrados S/MIME**|Las reglas solo pueden acceder a los encabezados de sobre y procesar los mensajes según las condiciones que se inspeccionan en los encabezados. <br/><br/> No se pueden procesar reglas con condiciones que requieran la inspección del contenido del mensaje ni acciones que pueden modificar dicho contenido.|
|**Mensajes protegidos por RMS**: mensajes a los que se ha aplicado una directiva de Active Directory Rights Management Services (AD RMS) o Azure Rights Management (RMS).|Las reglas siempre pueden acceder a los encabezados de sobre y procesar los mensajes según las condiciones que se inspeccionan en los encabezados. <br/><br/> Para que una regla inspeccione o modifique el contenido de un mensaje protegido por RMS, deberá comprobar que el descifrado de transporte está habilitado (como obligatorio u opcional; el valor predeterminado es Opcional).|
|**Mensajes con firma transparente**: mensajes que se han firmado pero no cifrado.|Sí|
|**Mensajes de mensajería unificada**: mensajes creados o procesados por el servicio de mensajería unificada, como correo de voz, fax, notificaciones de llamadas perdidas y mensajes creados o reenviados mediante Microsoft Outlook Voice Access.|Sí|
|**Mensajes anónimos**: mensajes enviados por remitentes anónimos.|Sí|
|**Informes de lectura**: informes que se generan en respuesta a las solicitudes de confirmación de lectura por parte de los remitentes. Los informes de lectura tienen una clase de mensaje de `IPM.Note*.MdnRead` o `IPM.Note*.MdnNotRead` .|Sí|

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- El valor de la propiedad **version** o **RuleVersion** de una regla no es importante en Exchange Online Protection.

- Después de crear o modificar una regla de flujo de correo, esta puede tardar hasta 30 minutos en aplicarse a los mensajes.

## <a name="for-more-information"></a>Más información

[Usar reglas de flujo de correo para inspeccionar datos adjuntos de mensajes en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Cifrado de correo electrónico en Office 365](../../compliance/email-encryption.md)

[Límites de reglas del diario, transporte y bandeja de entrada](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
