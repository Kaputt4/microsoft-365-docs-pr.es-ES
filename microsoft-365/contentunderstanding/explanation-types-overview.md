---
title: Tipos de explicación
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Más información sobre los tipos de explicación en Microsoft SharePoint Syntex
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087648"
---
# <a name="introduction-to-explanation-types"></a>Introducción a los tipos de explicación

Las explicaciones se utilizan para ayudar a definir la información que quiere etiquetar y extraer en los modelos de comprensión de documentos en Microsoft SharePoint Syntex. Cuando crea una explicación, debe seleccionar un tipo de explicación. Este artículo le ayuda a comprender los diferentes tipos de explicación y cómo se utilizan. 

   ![Tipos de explicación](../media/content-understanding/explanation-types.png) 
   
Estos son los tipos de explicación disponibles:

- **Lista de frases**: lista de palabras, frases, números u otros caracteres que se pueden usar en el documento o la información que se va a extraer. Por ejemplo, la cadena de texto **Médico remitente** está en todos los documentos de remisión médica que identifica.</br>

- **Lista de patrones**: enumera los modelos de números, letras u otros caracteres que se pueden utilizar para identificar la información que se está extrayendo. Por ejemplo, puede extraer el **número de teléfono** del médico remitente de todos los documentos de derivación médica que esté identificando.</br>

- **Proximidad**: describe lo cercanas que están las explicaciones entre sí. Por ejemplo, la lista de patrones de *número de la calle* se mostrará justo antes de la lista de frases de *nombre de la calle*, sin tokens entre ellas (aprenderá sobre los tokens más adelante en este artículo). El uso del tipo de proximidad requiere que tenga al menos dos explicaciones en su modelo o la opción se desactivará. 
 
## <a name="phrase-list"></a>Lista de frases

Un tipo de explicación de lista de frases se utiliza normalmente para identificar y clasificar un documento a través de su modelo. Como se describe en el ejemplo de etiqueta *Médico remitente*, se trata de una cadena de palabras, frases, números o caracteres que es coherente en los documentos que se están identificando.

Aunque no es un requisito, puede lograr un mayor éxito con su explicación si la frase que está registrando se encuentra en un lugar consistente en su documento. Por ejemplo, la etiqueta *Médico remitente* puede estar ubicada de manera uniforme en el primer párrafo del documento.

Si la distinción de mayúsculas y minúsculas es un requisito para identificar la etiqueta, usar el tipo Lista de frases le permite especificarla en la explicación si activa la casilla de verificación **Solo mayúsculas exactas**.

   ![Distinción entre mayúsculas y minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Listas de patrones

Un tipo de lista de patrones es especialmente útil cuando crea una explicación que identifica y extrae información de un documento. Por lo general, se presenta en diferentes formatos, como fechas, números de teléfono y números de tarjetas de crédito. Por ejemplo, una fecha se puede mostrar en varios formatos diferentes (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 de enero de 2020, etc.). Definir una lista de patrones hace que su explicación sea más eficiente, ya que captura cualquier posible variación en los datos que intenta identificar y extraer. 

Para el ejemplo del **número de teléfono**, extrae el número de teléfono de cada médico remitente de todos los documentos de remisión médica que identifica el modelo. Cuando cree la explicación, seleccione el tipo de lista Patrón para permitir los diferentes formatos que puede esperar que se devuelvan.

   ![Lista de patrones de números de teléfono](../media/content-understanding/pattern-list.png)

Para este ejemplo, active la casilla de verificación **Cualquier dígito entre 0-9** para reconocer cada valor "0" que se usa en la lista de patrones como un dígito entre 0 y 9.

   ![Cualquier dígito entre 0-9](../media/content-understanding/digit-identity.png)

De forma similar, si crea una lista de patrones que incluya caracteres de texto, active la casilla de verificación **Cualquier letra de la a a la z** para reconocer cada carácter "a" que se use en la lista de patrones como un carácter entre "a" y "z".

Por ejemplo, si crea una lista de patrones **Fecha** y desea asegurarse de que un formato de fecha como *el 1 de enero de 2020* se reconozca, tendrá que:
- Agregar *aaa 0, 0000* y *aaa 00, 0000* a la lista de patrones
- Asegúrese de que **Cualquier letra de la a a la z** también esté seleccionada.

   ![Cualquier letra de la a a la z](../media/content-understanding/any-letter.png)

Además, si tiene requisitos de uso de mayúsculas en su lista de patrones, tiene la opción de seleccionar la casilla de verificación **Solo mayúsculas y minúsculas exactas**. Para el ejemplo de fecha, si necesita que la primera letra del mes esté en mayúscula, debe:

- Agregar *Aaa 0, 0000* and *Aaa 00, 0000* a la lista de patrones.
- Asegúrese de que **Solo usar mayúsculas y minúsculas exactamente** también está seleccionado.

   ![Usar mayúsculas y minúsculas de forma exacta](../media/content-understanding/exact-caps.png)

> [!NOTE]
> En lugar de crear manualmente una explicación de las listas de patrones, utilice la [Biblioteca de explicación](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar plantillas de listas de patrones para las listas de patrones comunes, como *fecha*, *números de teléfono*, *número de tarjeta de crédito*, etc.

## <a name="proximity"></a>Proximidad 

El tipo de explicación de proximidad ayuda a su modelo a identificar los datos definiendo lo cerca que está otro dato. Por ejemplo, en su modelo ha definido dos explicaciones que etiquetan tanto el *Número de la dirección de la calle* como el *Número de teléfono* del cliente. 

Sabemos que los números de teléfono del cliente siempre aparecen antes que el número de la calle. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Use la explicación de proximidad para definir el número de teléfono que se debe desplazar para identificar mejor el número de la calle en los documentos.

   ![Explicación de Proximidad](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>¿Qué son los tokens?

Para poder usar el tipo de explicación de proximidad, necesita entender qué es un token, ya que la explicación de proximidad utiliza el número de tokens para medir la distancia entre una explicación y otra. Un token es un intervalo continuo (sin incluir espacios ni puntuación) de letras y números. 

En la siguiente tabla se muestran algunos ejemplos de cómo determinar el número de tokens en una frase.

|Frase|Número de tokens|Explicación|
|--|--|--|
|`Dog`|1|Una sola palabra sin signos de puntuación o espacios.|
|`RMT33W`|1|Un número de localizador de registros. Puede incluir números y letras, pero no tiene puntuación.|
|`425-555-5555`|5|Un número de teléfono. Cada signo de puntuación es un token único, por lo que `425-555-5555` tiene 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Configurar el tipo de explicación de proximidad

Para el ejemplo, configure el ajuste de proximidad de manera que podamos definir el rango del número de tokens en la explicación *Número de teléfono* a partir de la explicación *Número de la dirección de la calle*. Observe que el rango mínimo es "0", porque no hay tokens entre el número de teléfono y el número de la dirección.

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

   ![Ejemplo, Proximity](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a>Usar plantillas de explicación

Aunque se pueden agregar manualmente varios valores de la lista de patrones para la explicación, puede resultar más fácil usar las plantillas que se le proporcionan en la biblioteca de explicación.

Por ejemplo, en lugar de añadir manualmente todas las variaciones para *Fecha*, se puede utilizar la plantilla de la lista de patrones para *Fecha* que ya incluye una serie de valores de la lista de patrones:</br>

   ![Biblioteca de explicación](../media/content-understanding/explanation-template.png)</br>
 
La biblioteca de explicación incluye varias explicaciones de la lista de patrones más utilizados, entre las que se incluyen:</br>

- Fecha</br>
- Fecha (numérica)</br>
- Hora</br>
- Número</br>
- Número de teléfono</br>
- Código postal</br>
- Primera palabra de la frase</br>
- Tarjeta de crédito</br>
- Número de la seguridad social</br>

Tenga en cuenta que la biblioteca de explicación también incluye plantillas para las explicaciones de la lista de frases:
- Final de la oración
- Divisa

#### <a name="to-use-a-template-from-the-explanation-library"></a>Para usar una plantilla de la biblioteca de explicación

1. En la sección de **Explicaciones** de la página de **Entrenamiento** de su modelo, seleccione **Nuevo**, y luego seleccione **De Una Plantilla**.</br>

   ![Crear desde plantilla](../media/content-understanding/from-template.png)</br>

2.  En la página **Plantillas de explicación**, seleccione la explicación que desee usar y, a continuación, seleccione **Agregar**.</br>

       ![Seleccionar una plantilla](../media/content-understanding/phone-template.png)</br>

3. La información de la plantilla que ha seleccionado se mostrará en la página **Crear una explicación**. Si es necesario, edite el nombre de la explicación y agregue o elimine elementos de la lista de patrones.</br> 

   ![Editar plantilla](../media/content-understanding/phone-template-live.png)</br>

4. Cuando finalice, haga clic en **Guardar**.
