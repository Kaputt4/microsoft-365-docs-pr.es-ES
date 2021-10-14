---
title: Directivas de Cumplimiento de comunicaciones
description: Obtenga más información sobre las directivas de cumplimiento de comunicaciones.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: ddfa1a9e0e4fb622b03cec09429370fa25a2f11f
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "60336083"
---
# <a name="communication-compliance-policies"></a>Directivas de Cumplimiento de comunicaciones

## <a name="policies"></a>Directivas

> [!IMPORTANT]
> No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas en la [Microsoft 365 de cumplimiento de comunicaciones](https://compliance.microsoft.com/supervisoryreview).

Puede crear directivas de cumplimiento de comunicaciones para organizaciones de Microsoft 365 en el Centro de cumplimiento de Microsoft 365. Las directivas de cumplimiento de comunicación definen qué comunicaciones y usuarios están sujetos a revisión en su organización, definen las condiciones personalizadas que deben cumplir las comunicaciones y especifican quién debe hacer las revisiones. Los usuarios asignados *al* rol De administrador de cumplimiento de comunicaciones pueden configurar directivas y cualquier persona que tenga asignada esta función puede acceder a la página Cumplimiento de comunicaciones y a la configuración global del Centro de cumplimiento de Microsoft 365.  Si es necesario, puede exportar el historial de modificaciones de una directiva a un archivo .csv (valores separados por comas) que también incluya el estado de las alertas pendientes de revisión, los elementos escalados y los elementos resueltos. No se puede cambiar el nombre de las directivas y se pueden eliminar cuando ya no sea necesario.

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de directiva son configuraciones de directiva predefinidas que puede usar para crear rápidamente directivas para abordar escenarios de cumplimiento comunes. Cada una de estas plantillas tiene diferencias en las condiciones y el ámbito, y todas las plantillas usan los mismos tipos de señales de examen. Puede elegir entre las siguientes plantillas de directiva:

|**Área**|**Plantilla de directiva**|**Detalles**|
|:-----|:-----|:-----|
| **Lenguaje ofensivo y contra el acoso** | Supervisar las comunicaciones en busca de lenguaje ofensivo | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interno <br> - Porcentaje de revisión: 100% <br> - Condiciones: clasificador de idioma ofensivo |
| **Información confidencial** | Supervisar las comunicaciones para obtener información confidencial | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interno <br> - Porcentaje de revisión: 10% <br> - Condiciones: información confidencial, patrones de contenido y tipos integrados, opción de diccionario personalizado, datos adjuntos de más de 1 MB |
| **Cumplimiento normativo** | Supervisar las comunicaciones para obtener información relacionada con el cumplimiento normativo financiero | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente <br> - Porcentaje de revisión: 10% <br> - Condiciones: opción de diccionario personalizado, datos adjuntos de más de 1 MB |
| **Conflicto de intereses** | Supervisar las comunicaciones entre dos grupos o dos usuarios para ayudar a evitar conflictos de interés | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: interna <br> - Porcentaje de revisión: 100% <br> - Condiciones: Ninguna |

Las comunicaciones se examinan cada 24 horas a partir del momento en que se crean las directivas. Por ejemplo, si crea una directiva de idioma ofensivo a las 11:00 a.m., la directiva recopilará señales de cumplimiento de comunicaciones cada 24 horas a las 11:00 a.m. todos los días. La edición de una directiva no cambia esta vez. Para ver la última fecha y hora de examen de una directiva, vaya a la columna Último *examen de* directivas de la **página** Directiva. Después de crear una nueva directiva, puede tardar hasta 24 horas en ver la primera fecha y hora del examen de directivas. La fecha y la hora del último examen se convierten en la zona horaria del sistema local.

## <a name="pause-a-policy-preview"></a>Pausar una directiva (versión preliminar)

Después de crear una directiva de cumplimiento de comunicaciones, la directiva puede pausarse temporalmente si es necesario. La pausa de una directiva puede usarse para probar o solucionar problemas de coincidencias de directivas, o para optimizar las condiciones de la directiva. En lugar de eliminar una directiva en estas circunstancias, la pausa de una directiva también conserva las alertas y los mensajes de directiva existentes para las investigaciones y revisiones en curso. La pausa de una directiva impide la inspección y la generación de alertas para todas las condiciones de mensaje de usuario definidas en la directiva durante el tiempo en que se pausa la directiva. Para pausar o reiniciar una directiva, los usuarios deben ser miembros del grupo de roles *De administración de cumplimiento* de comunicaciones.

Para pausar una directiva, vaya a la **página** Directiva, seleccione una directiva y, a continuación, seleccione **Pausar directiva** en la barra de herramientas acciones. En el **panel Pausar** directiva, confirme que desea pausar la directiva **seleccionando Pausar**. En algunos casos, una directiva puede tardar hasta 24 horas en pausarse. Una vez pausada la directiva, no se crean alertas de mensajes que coincidan con la directiva. Sin embargo, los mensajes asociados con alertas creadas antes de pausar la directiva permanecen disponibles para investigación, revisión y corrección.

El estado de la directiva de las directivas en pausa puede indicar varios estados:

- **Activo:** la directiva está activa
- **En pausa:** la directiva está totalmente pausada.
- **Pausa:** la directiva está en proceso de pausa.
- **Reanudación:** la directiva en proceso de reanudación.
- **Error al reanudar:** se ha encontrado un error al reanudar la directiva. Para el seguimiento de la pila de errores, mantenga el mouse sobre *el estado Error al reanudar* en la columna Estado de la página Directiva.
- **Error al pausar:** se ha encontrado un error al pausar la directiva. Para el seguimiento de la pila de errores, mantenga el mouse sobre *el estado Error in pausing* en la columna Estado de la página Directiva.

Para reanudar una directiva, vaya a la **página** Directiva, seleccione una directiva y, a continuación, seleccione **Reanudar directiva** en la barra de herramientas acciones. En el **panel Desanudez** de directivas, confirme que desea reanudar la directiva seleccionando **Reanudar**. En algunos casos, una directiva puede tardar hasta 24 horas en reanudarse. Una vez que se reanude la directiva, se crearán alertas para los mensajes que coincidan con la directiva y estarán disponibles para investigación, revisión y corrección.

## <a name="copy-a-policy-preview"></a>Copiar una directiva (versión preliminar)

Para las organizaciones con directivas de cumplimiento de comunicaciones existentes, puede haber escenarios al crear una nueva directiva a partir de una directiva existente puede resultar útil. Copiar una directiva crea un duplicado exacto de una directiva existente, incluidos todos los usuarios del ámbito, todos los revisores asignados y todas las condiciones de directiva. Algunos escenarios pueden incluir:

- **Límite de almacenamiento de directivas alcanzado:** las directivas de cumplimiento de comunicaciones activas tienen límites de almacenamiento de mensajes. Cuando se alcanza el límite de almacenamiento de una directiva, la directiva se desactiva automáticamente. Las organizaciones que necesitan seguir detectando, capturando y actuando en mensajes inadecuados cubiertos por la directiva desactivada pueden crear rápidamente una nueva directiva con una configuración idéntica.
- **Detectar y revisar** mensajes inapropiados para diferentes grupos de usuarios: algunas organizaciones pueden preferir crear varias directivas con la misma configuración, pero incluyen diferentes usuarios en el ámbito y revisores diferentes para cada directiva.
- **Directivas similares con pequeños cambios:** para las directivas con configuraciones o condiciones complejas, puede ahorrar tiempo crear una nueva directiva a partir de una directiva similar.

Para copiar una directiva, los usuarios deben ser miembros de los grupos de roles *de* administración de cumplimiento de comunicaciones o cumplimiento *de* comunicaciones. Después de crear una nueva directiva a partir de una directiva existente, puede tardar hasta 24 horas en ver mensajes que coincidan con la nueva configuración de directiva.

Para copiar una directiva y crear una nueva directiva, siga estos pasos:

1. Seleccione la directiva que desea copiar.
2. Seleccione **Copiar botón de** barra de comandos de directiva en la barra de comandos o seleccione Copiar **directiva** en el menú de acciones de la directiva.
3. En el **panel Copiar directiva,** puede aceptar el nombre predeterminado de la directiva en el **campo Nombre** de directiva o cambiar el nombre de la directiva. El nombre de la directiva de la nueva directiva no puede ser el mismo que una directiva activa o desactivada existente. Complete el **campo Descripción** según sea necesario.
4. Si no necesita más personalización de la directiva, seleccione **Copiar directiva** para completar el proceso. Si necesita actualizar la configuración de la nueva directiva, seleccione **Personalizar directiva**. Esto inicia el asistente para directivas para ayudarle a actualizar y personalizar la nueva directiva.

## <a name="storage-limit-notification-preview"></a>Storage notificación de límite (versión preliminar)

Cada directiva de cumplimiento de comunicaciones tiene un tamaño límite de almacenamiento de 100 GB o 1 millón de mensajes, lo que se alcance primero. A medida que la directiva se acerca a estos límites, los correos electrónicos de notificación se envían automáticamente a los usuarios asignados a los grupos de roles De administración de cumplimiento de comunicaciones o cumplimiento *de* comunicaciones.  Los mensajes de notificaciones se envían cuando el tamaño de almacenamiento o el recuento de mensajes alcanzan el 80, 90 y el 95 por ciento del límite. Cuando se alcanza el límite de directiva, la directiva se desactiva automáticamente y la directiva deja de procesar mensajes para alertas.

>[!IMPORTANT]
>Si se desactiva una directiva debido a alcanzar los límites de almacenamiento y mensajes, asegúrese de evaluar cómo administrar la directiva desactivada. Si elimina la directiva, todos los mensajes, los datos adjuntos asociados y las alertas de mensajes se eliminarán permanentemente. Si necesita mantener estos elementos para su uso futuro, no elimine la directiva desactivada.

Para administrar las directivas que se acercan a los límites de almacenamiento y mensajes, considere la posibilidad de hacer una copia de la directiva para mantener la continuidad de la cobertura o realizar las siguientes acciones para ayudar a minimizar el tamaño de almacenamiento de directivas actual y los recuentos de mensajes:

- Considere la posibilidad de reducir el número de usuarios asignados a la directiva. Quitar usuarios de la directiva o crear diferentes directivas para diferentes grupos de usuarios puede ayudar a ralentizar el crecimiento del tamaño de la directiva y los mensajes totales.
- Examine la directiva en busca de alertas falsas positivas excesivas. Considere la posibilidad de agregar excepciones o cambios a las condiciones de la directiva para omitir las alertas falsas positivas comunes.
- Si una directiva ha alcanzado los límites de almacenamiento o mensaje y se ha desactivado, realice una copia de la directiva para seguir detectando y haciendo acciones para las mismas condiciones y usuarios.

## <a name="policy-settings"></a>Configuración de la directiva

### <a name="users"></a>Usuarios

Puede elegir seleccionar Todos los usuarios **o** definir usuarios específicos en una directiva de cumplimiento de comunicaciones. Al seleccionar **Todos los usuarios**, se aplica la directiva a todos los usuarios y a todos los grupos en los que se incluya cualquier usuario como miembro. Al definir usuarios específicos, la directiva se aplica a los usuarios definidos y a todos los grupos en los que los usuarios definidos se incluyan como miembro.

### <a name="direction"></a>Dirección

De forma predeterminada, **se muestra** la condición Dirección es y no se puede quitar. La configuración de dirección de comunicación en una directiva se elige individual o conjuntamente:

- **Entrante:** detecta las  comunicaciones enviadas a usuarios supervisados de remitentes externos e internos, incluidos otros usuarios supervisados en la directiva.
- **Saliente:** detecta las comunicaciones enviadas desde usuarios **supervisados** a destinatarios externos e internos, incluidos otros usuarios supervisados en la directiva.
- **Interno:** detecta las **comunicaciones entre** los usuarios o grupos supervisados en la directiva.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la directiva de cumplimiento de comunicaciones. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuenta bancaria, números de pasaporte y mucho más. Como parte de Información sobre la prevención de pérdida de [datos,](dlp-learn-about-dlp.md)la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar el contenido que puede ser confidencial. Los tipos de información confidencial predeterminados son:

- Financiera
- Medicina y salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea [Definiciones](sensitive-information-type-entity-definitions.md)de entidad de tipo de información confidencial .

### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizadas

Configure diccionarios de palabras clave personalizadas (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de su organización o sector. Los diccionarios de palabras clave admiten hasta 100 KB de términos (después de la compresión) en el diccionario y admiten cualquier idioma. El límite del espacio empresarial también es de 100 KB después de la compresión. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizadas a una sola directiva o tener un único diccionario de palabras clave por directiva. Estos diccionarios se asignan en una directiva de cumplimiento de comunicaciones y se pueden obtener desde un archivo (como una lista .csv o .txt) o desde una lista que puede importar en el Centro de cumplimiento [.](create-a-keyword-dictionary.md) Use diccionarios personalizados cuando necesite admitir términos o idiomas específicos de su organización y directivas.

### <a name="classifiers"></a>Clasificadores

Los clasificadores globales y capacitados integrados analizan los mensajes enviados o recibidos en todos los canales de comunicación de la organización en busca de diferentes tipos de problemas de cumplimiento. Los clasificadores usan una combinación de inteligencia artificial y de palabras clave para identificar lenguaje en los mensajes que es probable que infrinja las directivas contra el acoso. Actualmente, los clasificadores integrados admiten la identificación de palabras clave de mensaje en varios idiomas:

- Chino (simplificado)
- Inglés
- Francés
- Alemán
- Italiano
- Japonés
- Portugués
- Español

Los clasificadores globales y capacitados para el cumplimiento de la comunicación analizan las comunicaciones en busca de términos, imágenes y sentimientos para los siguientes tipos de idioma y contenido:

- **Imágenes para adultos:** busca imágenes sexualmente explícitas en la naturaleza.
- **Discriminación (versión preliminar):** busca un idioma discriminatorio explícito y es especialmente sensible al lenguaje discriminatorio frente a las comunidades afroestadounides/negras en comparación con otras comunidades.
- **Imágenes de gory:** busca imágenes que represente violencia y sangre.
- **Profanidad:** busca expresiones profanas que ensoñen a la mayoría de las personas.
- **Imágenes** rácidas: busca imágenes sexualmente sugerentes en la naturaleza, pero que contienen contenido menos explícito que las imágenes que se consideran adultos.
- **Hostigamiento dirigido:** busca conductas ofensivas dirigidas a personas relacionadas con la raza, el color, la religión, el origen nacional.
- **Amenaza:** busca amenazas para cometer violencia o daño físico a una persona o propiedad.

Los *clasificadores* de imágenes Adult, *Racy* y *Gory* analizan archivos en formatos .jpeg, .png, .gif y .bmp. El tamaño de los archivos de imagen debe ser inferior a 4 megabytes (MB) y las dimensiones de las imágenes deben ser mayores de 50 x 50 píxeles y superiores a 50 kilobytes (KB) para que la imagen pueda ser valorada. La identificación de imágenes es compatible Exchange Online mensajes de correo electrónico y Microsoft Teams canales y chats.

Los clasificadores globales y los clasificadores integrados no proporcionan una lista exhaustiva de términos o imágenes en estas áreas. Además, los estándares lingüísticos y culturales cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar clasificadores a su discreción. Aunque los clasificadores pueden ayudar a su organización a supervisar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de supervisión o dirección de su organización. Su organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen y el bloqueo del idioma y las imágenes en estas áreas, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft anima a consultar con abogados antes de la implementación y el uso.

> [!NOTE]
> Las directivas que usan clasificadores inspeccionarán y evaluarán los mensajes con un recuento de palabras de seis o más. Los mensajes que contienen menos de seis palabras no se evalúan en las directivas mediante clasificadores. Para identificar y tomar medidas en mensajes más cortos que contengan contenido inadecuado, se recomienda incluir un diccionario de palabras clave personalizado para supervisar las directivas de cumplimiento de comunicación para este tipo de contenido.

Para obtener información acerca de los clasificadores que se pueden entrenar en Microsoft 365, vea [Getting started with trainable classifiers](classifier-get-started-with.md).

### <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Configure directivas de cumplimiento de comunicación integradas o personalizadas para examinar e identificar texto impreso o escrito a mano de imágenes que puedan ser inapropiadas en su organización. La compatibilidad integrada de [Azure Cognitive Services](/azure/cognitive-services/computer-vision/overview-ocr) y el examen óptico para identificar texto en imágenes ayudan a los analistas e investigadores a detectar y actuar en casos en los que se puede perder una conducta inapropiada en comunicaciones que no son principalmente textuales.

Puede habilitar el reconocimiento óptico de caracteres (OCR) en nuevas directivas de plantillas, directivas personalizadas o actualizar directivas existentes para ampliar la compatibilidad con el procesamiento de imágenes incrustadas y datos adjuntos. Cuando se habilita en una directiva creada a partir de una plantilla de directiva, se admite el examen automático para imágenes incrustadas o adjuntas en el correo electrónico Microsoft Teams mensajes de chat. En el caso de las imágenes incrustadas en archivos de documento, no se admite el examen OCR. Para las directivas personalizadas, una o más configuraciones condicionales asociadas con palabras clave, clasificadores integrados o tipos de información confidencial deben configurarse en la directiva para habilitar la selección del examen OCR.

Las imágenes de 50 KB a 4 MB en los siguientes formatos de imagen se examinan y procesan:

- .jpg/.jpeg (grupo de expertos fotográficos conjuntos)
- .png (gráficos de red portátiles)
- .bmp (mapa de bits)
- .tiff (formato de archivo de imagen de etiqueta)
- .pdf (formato de documento portátil)

> [!NOTE]
> Actualmente, el examen y la extracción de imágenes .pdf incrustadas y adjuntas solo se admiten para los mensajes de correo electrónico.

Al revisar alertas pendientes para directivas con OCR habilitado, las imágenes identificadas y coincidentes con las condiciones de directiva se muestran como elementos secundarios para las alertas asociadas. Puede ver la imagen original para evaluar el texto identificado en contexto con el mensaje original. Las imágenes detectadas pueden tardar hasta 48 horas en estar disponibles con alertas.

### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la directiva se aplican a las comunicaciones tanto de correo electrónico como de orígenes de terceros de su organización (como de Instant Bloomberg).

En la tabla siguiente se explica más sobre cada condición.

|**Condition**|**Cómo usar esta condición**|
|:-----|:-----|
| **El contenido coincide con cualquiera de estos clasificadores** | Aplicar a la directiva cuando se incluyan o excluyan los clasificadores en un mensaje. Algunos clasificadores están predefinidos en el espacio empresarial y los clasificadores personalizados deben configurarse por separado antes de que estén disponibles para esta condición. Solo se puede definir un clasificador como una condición en una directiva. Para obtener más información acerca de la configuración de clasificadores, vea [Learn about trainable classifiers (preview).](classifier-learn-about.md) |
| **El contenido contiene cualquiera de estos tipos de información confidencial** | Se aplica a la directiva cuando se incluya o excluya cualquier tipo de información confidencial en un mensaje. Algunos clasificadores están predefinidos en el espacio empresarial y los clasificadores personalizados se pueden configurar por separado o como parte del proceso de asignación de condiciones. Cada tipo de información confidencial que elija se aplica por separado y solo uno de estos tipos de información confidencial debe aplicar para que la directiva se aplique al mensaje. Para obtener más información acerca de los tipos de información confidencial personalizados, vea [Learn about sensitive information types](sensitive-information-type-learn-about.md). |
| **El mensaje se recibe desde cualquiera de estos dominios**  <br><br> **El mensaje no se recibe de ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico especificado se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea examinar todo el correo electrónico de un dominio específico, pero desea excluir los mensajes que no necesitan  revisión (boletines, anuncios, entre otros), debe configurar que un mensaje no se reciba desde ninguna condición de estos dominios que excluya la dirección de correo electrónico (ejemplo "newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios**  <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes enviados. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea examinar todo el correo electrónico enviado a un dominio específico, pero desea excluir los mensajes enviados que no necesitan revisión, debe configurar dos condiciones: <br> - Se **envía un mensaje a cualquiera de estos dominios** condición que define el dominio ("contoso.com"), AND <br> - Un **mensaje no se envía a ninguna condición de estos** dominios que excluya la dirección de correo electrónico ("subscriptions@contoso.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas**  <br><br> **El mensaje no se clasifica con ninguna de estas etiquetas** | Para aplicar la directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención deben configurarse por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo una de estas etiquetas debe aplicar para que la directiva se aplique al mensaje). Para obtener más información acerca de las etiquetas de retención, vea [Learn about retention policies and retention labels](retention.md).|
| **El mensaje contiene cualquiera de estas palabras**  <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en un mensaje, escriba cada palabra separada con una coma. Para frases de dos o más palabras, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-policies.md#Matchwords).|
| **Los datos adjuntos contienen cualquiera de estas palabras**  <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en los datos adjuntos de un mensaje (como un documento de Word), escriba cada palabra separada con una coma. Para frases de dos o más palabras, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-policies.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo**  <br><br> **Los datos adjuntos no son ninguno de estos tipos de archivo** | Para supervisar las comunicaciones que incluyen o excluyen tipos específicos de datos adjuntos, escriba las extensiones de archivo (como .exe o .pdf). Si desea incluir o excluir varias extensiones de archivo, escriba estas en líneas independientes. Solo debe coincidir una extensión de datos adjuntos para que se aplique la directiva.|
| **El tamaño del mensaje es mayor que**  <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes en función de un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que esté sujeto a revisión. Por ejemplo, si especifica que **el** tamaño del mensaje es mayor que \> **1,0 MB,** todos los mensajes de 1,01 MB o más están sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **Los datos adjuntos son mayores que**  <br><br> **Los datos adjuntos no son mayores que** | Para revisar los mensajes en función del tamaño de sus datos adjuntos, especifique el tamaño máximo o mínimo que puede tener un archivo adjunto antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si  especifica Que datos adjuntos supere \> **los 2,0 MB,** todos los mensajes con datos adjuntos de 2,01 MB o más estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|

#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada palabra que escriba y separe con una coma se aplica por separado (solo debe aplicarse una palabra para que la condición de directiva se aplique al correo electrónico o los datos adjuntos). Por ejemplo, vamos a usar la condición, **Message** contiene cualquiera de estas palabras , con las palabras clave "banker", "confidential" y "insider trading" separadas por una coma (banker, confidential,"insider trading"). La directiva se aplica a cualquier mensaje que incluya la palabra "banker", "confidential" o la frase "insider trading". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o los datos adjuntos deben coincidir exactamente con lo que escriba.

> [!IMPORTANT]
>
> Al importar un archivo de diccionario personalizado, cada palabra o frase debe separarse con un retorno de carro y en una línea independiente. Por ejemplo:
>
> *banker* <br>
> *confidencial* <br>
> *insider trading*

Para examinar los mensajes de correo electrónico y [](create-a-keyword-dictionary.md) los datos adjuntos de las mismas palabras clave, cree un diccionario de palabras clave personalizado para los términos que desea examinar en los mensajes. Esta configuración de directiva identifica palabras clave definidas que aparecen en el mensaje de correo **electrónico O en** los datos adjuntos del correo electrónico. El uso de la configuración de directiva condicional estándar (*Message* contiene cualquiera de estas palabras y Attachment  *contiene* cualquiera de estas palabras ) para identificar los términos de los mensajes y los datos adjuntos requiere que los términos se presenten tanto en el mensaje como en los datos adjuntos.

#### <a name="enter-multiple-conditions"></a>Especificar varias condiciones

Si especifica varias condiciones, Microsoft 365 todas las condiciones juntas para determinar cuándo aplicar la directiva de cumplimiento de comunicación a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la directiva, a menos que especifique una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "trade" y es mayor que 2 MB. Sin embargo, si el mensaje también contiene las palabras "Aprobado por Contoso financial", la directiva no debe aplicarse. En este ejemplo, las tres condiciones se definirían de la siguiente manera:

- **El mensaje contiene cualquiera de estas palabras**, con la palabra clave "trade"
- **El tamaño del mensaje es mayor que**, con el valor 2 MB
- **El mensaje no contiene ninguna de estas palabras**, con las palabras clave "Aprobado por el equipo financiero de Contoso"

### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones regida por una directiva de cumplimiento de comunicaciones. Se selecciona una muestra de contenido aleatoria en tiempo real del porcentaje total de contenido que coincida con las condiciones de directiva elegidas. Si quiere que los revisores revisen todos los elementos, puede configurar el **100 %** en una directiva de cumplimiento de comunicaciones.

## <a name="alert-policies"></a>Directivas de alerta

Después de configurar una directiva, se crea automáticamente una directiva de alerta correspondiente y se generan alertas para los mensajes que coinciden con las condiciones definidas en la directiva. Puede tardar hasta 24 horas después de crear una directiva de inicio para recibir alertas de indicadores de actividad. De forma predeterminada, todos los desencadenadores de alerta de coincidencias de directiva tienen asignado un nivel de gravedad de medio en la directiva de alerta asociada. Las alertas se generan para una directiva de cumplimiento de comunicaciones una vez que se cumple el nivel de umbral de desencadenador de agregación en la directiva de alerta asociada.

Para las directivas de cumplimiento de comunicaciones, los siguientes valores de directiva de alerta están configurados de forma predeterminada:

|**Desencadenador de directiva de alerta**|**Valor predeterminado**|
|:-----|:-----|
| Agregación | Agregación sencilla |
| Umbral | Valor predeterminado: 4 actividades <br> Mínimo: 3 actividades <br> Máximo: 2.147.483.647 actividades |
| Window | Valor predeterminado: 60 minutos <br> Mínimo: 60 minutos <br> Máximo: 10.000 minutos |

> [!NOTE]
> La configuración del desencadenador de umbral de directiva de alerta para actividades admite un valor mínimo de 3 o superior para las directivas de cumplimiento de comunicaciones.

Puede cambiar la configuración predeterminada para desencadenadores en número de actividades, período para  las actividades y para usuarios específicos en directivas de alerta en la página Directivas de alerta de la Centro de cumplimiento de Microsoft 365.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Cambiar el nivel de gravedad de una directiva de alerta

Si desea cambiar el nivel de gravedad asignado en una directiva de alerta para una directiva de cumplimiento de comunicación específica, siga estos pasos:

1. Inicie sesión [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el Centro de cumplimiento de Microsoft 365, vaya a **Directivas**.

3. Seleccione **Office 365 alerta en** la página **Directivas** para abrir la página Directivas **de** alertas.

4. Active la casilla de verificación de la directiva de cumplimiento de comunicaciones que desea actualizar y, a continuación, **seleccione Editar directiva**.

5. En la **pestaña Descripción,** seleccione el desplegable **Gravedad** para configurar el nivel de alerta de directiva.

6. Seleccione **Guardar** para aplicar el nuevo nivel de gravedad a la directiva.

7. Seleccione **Cerrar para** salir de la página de detalles de la directiva de alertas.
