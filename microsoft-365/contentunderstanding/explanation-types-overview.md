---
title: Tipos de explicación en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga más información sobre la lista de frases, las expresiones regulares y los tipos de explicación de proximidad en Microsoft SharePoint Syntex.
ms.openlocfilehash: ae31ee3e4d9550c54f884360f3beea960db47b20
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824792"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a>Tipos de explicación en Microsoft SharePoint Syntex

Las explicaciones se utilizan para ayudar a definir la información que desea etiquetar y extraer en los modelos de comprensión de documentos en Microsoft SharePoint Syntex. Al crear una explicación, debe seleccionar un tipo de explicación. Este artículo le ayudará a comprender los distintos tipos de explicación y cómo se usan.

![Captura de pantalla del panel Crear una explicación que muestra los tres tipos de explicación.](../media/content-understanding/explanation-types.png)

Estos son los tipos de explicación disponibles:

- [**Lista de frases**](#phrase-list): lista de palabras, frases, números u otros caracteres que se pueden usar en el documento o la información que se va a extraer. Por ejemplo, la cadena de texto *médico remitente* está en todos los documentos de derivación médica que identifica. O la cadena *número de teléfono* del médico remitente está en todos los documentos de derivación médica que identifica.

- [**Expresión regular**](#regular-expression): usa una notación que coincida con patrones de caracteres específicos. Por ejemplo, puede usar una expresión regular para buscar todas las instancias de una *dirección de correo electrónico* en un conjunto de documentos.

- [**Proximidad**](#proximity): describe la cercanía que existe entre varias explicaciones. Por ejemplo, el *número de la calle* se mostrará justo antes de la lista de *nombre de la calle*, sin tokens entre ellas (aprenderá sobre los tokens más adelante en este artículo). Usar el tipo de proximidad requiere que tenga al menos dos explicaciones en su modelo o la opción se deshabilitará.

## <a name="phrase-list"></a>Lista de frases

Un tipo de explicación de la lista de frases se usa normalmente para identificar y clasificar un documento a través del modelo. Como se describe en el ejemplo de etiqueta *médico remitente*, se trata de una cadena de palabras, frases, números o caracteres que aparece uniformemente en los documentos que se identifican.

Aunque no es obligatorio, puede tener más éxito con su explicación si la frase que captura se encuentra habitualmente en el mismo lugar en los documentos. Por ejemplo, puede que la etiqueta *médico remitente* se encuentre siempre en el primer párrafo del documento. También puede usar la opción avanzada **[Configurar dónde aparecen las frases en el documento](explanation-types-overview.md#configure-where-phrases-occur-in-the-document)** para seleccionar áreas específicas donde se encuentra la frase, especialmente si existe la posibilidad de que la frase aparezca en varias ubicaciones del documento.

Si la distinción de mayúsculas y minúsculas es un requisito para identificar la etiqueta, usar el tipo Lista de frases le permite especificarla en la explicación si activa la casilla de verificación **Solo mayúsculas exactas**.

![Distinción entre mayúsculas y minúsculas.](../media/content-understanding/case-sensitivity.png)

Un tipo de frase es especialmente útil cuando crea una explicación que identifica y extrae información en diferentes formatos, como fechas, números de teléfono y números de tarjetas de crédito. Por ejemplo, una fecha puede mostrarse en diferentes formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 de enero de 2020, etc.). Definir una lista de frases hace que su explicación sea más eficiente cuando capture cualquier posible variación en los datos que trata de identificar y extraer.

Para el ejemplo del *número de teléfono*, extraiga el número de teléfono de cada médico remitente de todos los documentos de derivación médica que el modelo identifique. Cuando cree la explicación, escriba los distintos formatos que pueda mostrar un número de teléfono en el documento para poder capturar posibles variaciones.

![Patrones de frases de número de teléfono.](../media/content-understanding/pattern-list.png)

Para este ejemplo, en **Configuración avanzada**, seleccione la casilla **Cualquier dígito entre 0 y 9** para reconocer cada valor de "0" usado en la lista de frases para ser cualquier dígito del 0 al 9.

![Cualquier dígito entre 0-9.](../media/content-understanding/digit-identity.png)

De forma similar, si crea una lista de frases que incluya caracteres de texto, active la casilla de verificación **Cualquier letra de la a a la z** para reconocer cada carácter "a" que se use en la lista de frases como un carácter entre "a" y "z".

Por ejemplo, si crea una lista de frases de **Fecha** y quiere asegurarse de que un formato de fecha como *1 de enero de 2020* se reconozca, tendrá que:

- Agregar *aaa 0, 0000* y *aaa 00, 0000* a la lista de frases.
- Asegúrese de que **Cualquier letra de la a a la z** también esté seleccionada.

![Cualquier letra de la a a la z.](../media/content-understanding/any-letter.png)

Si tiene requisitos de usar mayúsculas y minúsculas en su lista de frases, puede seleccionar la casilla de verificación **Solo usar mayúsculas y minúsculas exactamente**. Para el ejemplo de fecha, si requiere que la primera letra del mes esté en mayúscula, debe:

- Agregar *Aaa 0, 0000* y *Aaa 00, 0000* a la lista de frases.
- Asegúrese de que **Solo usar mayúsculas y minúsculas exactamente** también está seleccionado.

![Solo mayúsculas y minúsculas exactas.](../media/content-understanding/exact-caps.png)

> [!NOTE]
> En lugar de crear manualmente una explicación de las listas de frases, utilice la [Biblioteca de explicación](explanation-templates.md) para usar plantillas de listas de frases para las listas de frases comunes, como *fecha*, *números de teléfono* o *número de tarjeta de crédito*.

## <a name="regular-expression"></a>Expresión regular

Un tipo de explicación de expresiones regulares le permite crear patrones que ayudan a buscar e identificar determinadas cadenas de texto en los documentos. Puede usar expresiones regulares para analizar rápidamente grandes cantidades de texto de la siguiente manera:

- Buscar patrones de caracteres específicos.
- Validar el texto para asegurarse de que coincida con un patrón predefinido (por ejemplo, una dirección de correo electrónico).
- Extraer, editar, reemplazar o eliminar subcadenas de texto.

Un tipo de expresión regular es especialmente útil cuando se crea una explicación que identifica y extrae información en formatos regulares, como direcciones de correo electrónico, números de cuentas bancarias o direcciones URL. Por ejemplo, una dirección de correo electrónico, como megan@contoso.com, se muestra siempre con un patrón determinado (en el ejemplo, "megan" es la primera parte y "com" es la última).

La expresión regular de una dirección de correo electrónico es: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.

Esta expresión se compone de cinco partes, en este orden:

1. cualquier cantidad de los siguientes caracteres:

   a. Letras de la "a" a la "z"

   b. Números del 0 al 9

   c. Punto, subrayado, porcentaje o guion

2. El símbolo @

3. cualquier cantidad de los mismos caracteres como en la primera parte de la dirección de correo electrónico

4. Un punto

5. De dos a seis letras

Para agregar un tipo de explicación de expresiones regulares:

1. Desde el panel **Crear una explicación**, en **Tipo de explicación**, seleccione la **Expresión regular**.

   ![Captura de pantalla que muestra el panel Crear una explicación con la expresión regular seleccionada.](../media/content-understanding/create-regular-expression.png)

2. Puede escribir una expresión en el cuadro de texto **Expresión regular** o seleccionar **Agregar una expresión regular desde una plantilla**.

   Cuando agregue una expresión regular con una plantilla, el nombre y la expresión regular se agregarán automáticamente al cuadro de texto. Por ejemplo, si elige la plantilla **dirección de correo electrónico**, se rellenará el panel **Crear una explicación**.

   ![Captura de pantalla que muestra el panel Crear una explicación con la plantilla de dirección de correo electrónico aplicada.](../media/content-understanding/create-regular-expression-email.png)

### <a name="limitations"></a>Limitaciones

En la tabla siguiente, se muestran las opciones de caracteres en línea que no están disponibles actualmente para su uso en patrones de expresiones regulares.

|Opción|Estado|Funcionalidad actual|
|---|---|---|
|Distinción entre mayúsculas y minúsculas|No se admite actualmente.|No hay distinción entre mayúsculas y minúsculas en todas las coincidencias que se obtienen.|
|Anclajes de línea|No se admite actualmente.| No se puede especificar una posición específica en una cadena en la que debe producirse una coincidencia.|

## <a name="proximity"></a>Proximidad

El tipo de explicación de proximidad ayuda al modelo a identificar los datos definiendo la proximidad que otros datos tienen con estos. Por ejemplo, en su modelo ha definido dos explicaciones que etiquetan tanto el *número de la dirección de la calle* como el *número de teléfono* del cliente.

Sabemos que los números de teléfono del cliente siempre aparecen antes que el número de la calle.

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Use la explicación de proximidad para definir el número de teléfono que se debe desplazar para identificar mejor el número de la calle en los documentos.

![Explicación de proximidad.](../media/content-understanding/proximity.png)

> [!NOTE]
> Actualmente, las expresiones regulares no se pueden usar con el tipo de explicación de proximidad.

#### <a name="what-are-tokens"></a>¿Qué son los tokens?

Para usar el tipo de explicación de proximidad es necesario comprender qué es un token. El número de tokens muestra cómo la explicación de proximidad mide la distancia entre una explicación y otra. Un token es un intervalo continuo (sin incluir espacios ni signos de puntuación) de letras y números.

En la siguiente tabla se muestran algunos ejemplos de cómo determinar el número de tokens en una frase.

|Frase|Número de tokens|Explicación|
|---|---|---|
|`Dog`|1|Una sola palabra sin signos de puntuación o espacios.|
|`RMT33W`|1|Un número de localizador de registros. Puede incluir números y letras, pero no signos de puntuación.|
|`425-555-5555`|5|Un número de teléfono Cada signo de puntuación es un token único, por lo que `425-555-5555` tiene 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555`|
|`https://luis.ai`|7 |`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`|

#### <a name="configure-the-proximity-explanation-type"></a>Configurar el tipo de explicación de proximidad

Para el ejemplo, configure el ajuste de proximidad de manera que podamos definir el rango del número de tokens en la explicación *número de teléfono* a partir de la explicación *número de la dirección de la calle*. Vea que el intervalo mínimo es "0", ya que no hay ningún token entre el número de teléfono y el número de la dirección postal.

Sin embargo, algunos números de teléfono de los documentos de muestra incluyen *(móvil)* al final.

Nestor Wilke<br>
111-111-1111 (móvil)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Hay tres tokens en *(móvil)*:

|Frase|Cuenta de tokens|
|--|--|
|(|1|
|móvil|2|
|)|3|

Configure la opción de proximidad para tener un intervalo de 0 a 3.

![Ejemplo de proximidad.](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a>Configurar dónde aparecen frases en el documento

Cuando crea una explicación, de forma predeterminada se busca en todo el documento la frase que intenta extraer. Sin embargo, puede usar la opción avanzada **Dónde se aparezcan estas frases** para ayudar a aislar una ubicación específica del documento donde aparezca una frase. Esta configuración es útil cuando pueden aparecer instancias similares de una frase en otra parte del documento y quiere asegurarse de que se ha seleccionado la correcta.

Si nos referimos a nuestro ejemplo de documento de derivación médica, siempre se menciona el *médico remitente* en el primer párrafo del documento. Con la opción **Dónde se aparezcan estas frases**, en este ejemplo puede configurar su explicación para que busque esta etiqueta solo en la sección inicial del documento o en cualquier otra ubicación en la que pueda aparecer.

![Opción Dónde aparezcan estas frases.](../media/content-understanding/phrase-location.png)

Puede seleccionar una de las siguientes opciones para este valor:

- En cualquier lugar del archivo: se busca la frase en todo el documento.

- Principio del archivo: se busca en el documento desde el principio hasta la ubicación de la frase.

   ![Principio del archivo.](../media/content-understanding/beginning-of-file.png)

    En el visor, puede ajustar manualmente el cuadro de selección para que incluya la ubicación donde aparezca la fase. El valor **Posición final** se actualizará para mostrar el número de tokens que incluye el área seleccionada. Puede actualizar el valor de la **posición final** para ajustar el área seleccionada.

   ![Cuadro de posición Principio del archivo.](../media/content-understanding/beginning-box.png)

- Final del archivo: se busca en el documento desde el principio hasta la ubicación de la frase.

   ![Final del archivo.](../media/content-understanding/end-of-file.png)

    En el visor, puede ajustar manualmente el cuadro de selección para que incluya la ubicación donde aparezca la fase. El valor **Posición inicial** se actualizará para mostrar el número de tokens que incluye el área seleccionada. También puede actualizar el valor Posición inicial para ajustar el área seleccionada.

   ![Cuadro de posición Final del archivo.](../media/content-understanding/end-box.png)

- Intervalo personalizado: se busca dentro de un rango especificado en el documento.

   ![Intervalo personalizado.](../media/content-understanding/custom-file.png)

    En el visor, puede ajustar manualmente el cuadro de selección para que incluya la ubicación donde aparezca la fase. Para esta opción, necesita seleccionar una posición **Inicio** y una posición **Fin**. Estos valores representan el número de tokens desde el principio del documento. Aunque puede escribir los valores manualmente, es más fácil ajustarlos en el cuadro de selección en el visor.

## <a name="considerations-when-configuring-explanations"></a>Consideraciones al configurar explicaciones

Al entrenar un clasificador, hay que tener en cuenta algunas cosas que producirán resultados más predecibles:

- Cuantos más documentos entrene, más preciso será el clasificador.  Cuando sea posible, use más de 5 documentos correctos y use más de 1 documento incorrecto.  Si las bibliotecas con las que trabaja tienen varios tipos de documento diferentes, varios de cada tipo dan lugar a resultados más predecibles.
- El etiquetado del documento desempeña un papel importante en el proceso de entrenamiento.  Se usan junto con explicaciones para entrenar el modelo.  Es posible que vea algunas anomalías al entrenar un clasificador con documentos que no tienen mucho contenido en ellos.  Es posible que la explicación no coincida con nada en el documento, pero dado que se ha etiquetado como un documento "bueno", es posible que vea que es una coincidencia durante el entrenamiento.
- Al crear explicaciones, usa lógica OR en combinación con la etiqueta para determinar si es una coincidencia.  La expresión regular que usa la lógica AND puede ser más predecible.  Esta es una expresión regular de ejemplo que se usará en documentos reales como entrenamiento.  Tenga en cuenta que el texto resaltado en rojo es la frase que está buscando.

    <pre>(?=.*network provider)(?=.*participating providers).*</pre>

- Las etiquetas y explicaciones funcionan conjuntamente y se usan en el entrenamiento del modelo.  No se trata de una serie de reglas que se pueden desa acoplar y aplicar pesos precisos o predicción a cada variable que se haya configurado.  Cuanto mayor sea la variación de los documentos utilizados en el entrenamiento, se proporcionará más precisión en el modelo.

### <a name="see-also"></a>Ver también

[Use plantillas de explicación en SharePoint Syntex](explanation-templates.md)
