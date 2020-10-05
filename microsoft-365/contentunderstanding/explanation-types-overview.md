---
title: Tipos de explicación
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Más información sobre los tipos de explicación en Microsoft SharePoint Syntex
ms.openlocfilehash: 43272504912451e4690cb8b7fe351462371bb252
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350308"
---
# <a name="introduction-to-explanation-types"></a>Introducción a los tipos de explicación

Las explicaciones se utilizan para ayudar a definir la información que desea etiquetar y extraer en los modelos de comprensión de documentos en Microsoft SharePoint Syntex. Al crear una explicación, debe seleccionar un tipo de explicación. Este artículo le ayudará a obtener más información sobre los distintos tipos de explicación y cómo se usan. 

   ![Tipos de explicación](../media/content-understanding/explanation-types.png) 
   
Estos son los tipos de explicación disponibles:

- **Lista de frases**: lista de palabras, frases, números u otros caracteres que se pueden usar en el documento o la información que se va a extraer. Por ejemplo, la cadena de texto: **el médico remitente** está en todos los documentos de referencia médica que está identificando.</br>

- ** Lista de patrones:** enumera los modelos de números, letras u otros caracteres que se pueden utilizar para identificar la información que se está extrayendo. Por ejemplo, puede extraer el **número de teléfono** del médico remitente de todos los documentos de referencia médica que está identificando.</br>

- **Proximidad:** Describe cómo se aproximan las explicaciones entre sí. Por ejemplo, el *número de la calle* se mostrará justo antes de la lista de *nombre de la calle*, sin tokens entre ellas (aprenderá sobre los tokens más adelante en este artículo). Usar el tipo de proximidad requiere que tenga al menos dos explicaciones en su modelo o la opción se deshabilitará. 
 
## <a name="phrase-list"></a>Lista de frases

Un tipo de explicación de la lista de frases se usa normalmente para identificar y clasificar un documento a través del modelo. Como se describe en el ejemplo de etiqueta *médico remitente*, se trata de una cadena de palabras, frases, números o caracteres que es coherente en los documentos que se están identificando.

Aunque no es un requisito, puede lograr un mayor éxito con su explicación si la frase que está registrando se encuentra en un lugar consistente en su documento. Por ejemplo, puede que la etiqueta*médico remitente* se encuentre sistemáticamente en el primer párrafo del documento.

Si la distinción de mayúsculas y minúsculas es un requisito para identificar la etiqueta, usar el tipo Lista de frases le permite especificarla en la explicación si activa la casilla de verificación **Solo mayúsculas exactas**.

   ![Distinción entre mayúsculas y minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Listas de patrones

Un tipo de lista de patrones es especialmente útil cuando se crea una explicación que identifica y extrae la información de un documento. Por lo general, se presenta en diferentes formatos, como fechas, números de teléfono o números de tarjeta de crédito. Por ejemplo, una fecha puede ser mostrada en diferentes formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 de enero de 2020, etc.). Definir una lista de patrones hace que su explicación sea más eficiente al capturar cualquier posible variación en los datos que está tratando de identificar y extraer. 

Para el ejemplo del **número de teléfono**, extraiga el número de teléfono de cada médico remitente de todos los documentos de remisión médica que el modelo identifica. Cuando cree la explicación, seleccione el tipo Lista de patrones para permitir que se devuelvan los distintos formatos que esperaba.

   ![Lista de patrones de números de teléfono](../media/content-understanding/pattern-list.png)

Para este ejemplo, active la casilla de verificación **Cualquier dígito entre 0-9**. Si selecciona esta opción, el valor "0" que se usa en la lista de patrones se reconoce como cualquier dígito entre 0 y 9.

   ![Cualquier dígito entre 0-9](../media/content-understanding/digit-identity.png)

De forma similar, si crea una lista de patrones que incluya caracteres de texto, active la casilla de verificación **Cualquier letra de la a a la z**. Al seleccionar esta opción se reconoce cada carácter "a" que se usa en la lista trama para que sea cualquier carácter entre "a" y "z".

Por ejemplo, si crea una lista de patrones**Fecha** y desea asegurarse de que un formato de fecha como *el 1 de enero de 2020* se reconozca, tendrá que:
- Agregar *aaa 0, 0000* y *aaa 00, 0000* a la lista de patrones
- Asegúrese de que **Cualquier letra de la a a la z** también esté seleccionada.

   ![Cualquier letra de la a a la z](../media/content-understanding/any-letter.png)

Además, si tiene requisitos de usar mayúsculas y minúsculas en su lista de patrones, tiene la opción de seleccionar la casilla de verificación **Solo usar mayúsculas y minúsculas exactamente**. En el ejemplo de la fecha, si necesita que la primera letra del mes se ponga en mayúsculas, deberá:

- Agregar *Aaa 0, 0000 * y *Aaa 00, 0000* a la lista de patrones.
- Asegúrese de que **Solo usar mayúsculas y minúsculas exactamente** también está seleccionado.

   ![Solo usar mayúsculas y minúsculas exactamente](../media/content-understanding/exact-caps.png)

> [!NOTE]
> En lugar de crear manualmente una explicación de las listas de patrones, utilice la[biblioteca de explicación ](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar plantillas de listas de patrones predefinidas para las listas de patrones comunes, como *fecha*, *números de teléfono*, *número de tarjeta de crédito*, etc. 

## <a name="proximity"></a>Proximidad 

El tipo explicación de la proximidad ayuda a que el modelo identifique los datos en la definición de cómo se cierra otro elemento de datos. Por ejemplo, en el modelo, ha definido dos explicaciones que etiquetan tanto el *Número de la dirección de la calle* como el *número de teléfono* del cliente. 

También tiene en cuenta que los números de teléfono del cliente siempre aparecen antes que el número de la calle. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Use la explicación de proximidad para definir el número de teléfono que se debe desplazar para identificar mejor el número de la calle en los documentos.

   ![Explicación de Proximidad](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>¿Qué son los tokens?

Para poder usar el tipo de explicación de proximidad, necesita entender qué es un token, ya que la explicación de proximidad utiliza el número de tokens para medir la distancia entre una explicación y otra.  

Un token es un intervalo continuo (sin espacios ni signos de puntuación) de letras y números. Un espacio NO es un token. Cada signo de puntuación es un token. En la siguiente tabla se muestran algunos ejemplos de cómo determinar el número de tokens en una frase.

|Frase|Número de tokens|Explicación|
|--|--|--|
|`Dog`|1|Una sola palabra sin signos de puntuación o espacios.|
|`RMT33W`|1|Un número de localizador de registros. Es posible que tenga números y letras, pero no tiene signos de puntuación.|
|`425-555-5555`|5|Un número de teléfono Cada signo de puntuación es un token único, por lo que  `425-555-5555` serían 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Configurar el tipo de explicación de proximidad

Para la muestra, configure el ajuste de proximidad de manera que podamos definir el rango del número de tokens que la explicación es del*número de teléfono*la explicación es del *número de la dirección de la calle*.

Debería ver que el intervalo mínimo es "0", ya que no hay ningún token entre el número de teléfono y el número de la dirección postal.

Sin embargo, algunos números de teléfono de los documentos de muestra se adjuntan con *(móvil)*.

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

Aunque se pueden agregar manualmente varios valores de la lista de patrones para la explicación, puede resultar mucho más fácil usar las plantillas creadas previamente que se le proporcionan en la biblioteca de explicación.

Por ejemplo, en lugar de añadir manualmente todas las variaciones para *Fecha*, se puede utilizar la plantilla de la lista de patrones para *Fecha*que ya incluye una serie de valores de la lista de patrones:</br>

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

Tenga en cuenta que la biblioteca de explicación también incluye plantillas para las explicaciones de la lista de frases, entre las que se incluyen:
- Final de la oración
- Divisa

#### <a name="to-use-a-template-from-the-explanation-library"></a>Para usar una plantilla de la biblioteca de explicación

1. En la sección de **Explicaciones** de la página de ** Entrenamiento **de su modelo, seleccione**Nuevo**, y luego seleccione**De Una Plantilla**.</br>

   ![Crear desde plantilla](../media/content-understanding/from-template.png)</br>

2.  En la página **plantillas de explicación**, seleccione la explicación que desee usar y, a continuación, seleccione **agregar**.</br>

       ![Seleccionar una plantilla](../media/content-understanding/phone-template.png)</br>

3. La información de la plantilla que ha seleccionado se mostrará en la página **crear una explicación**. Si es necesario, edite el nombre de la explicación y agregue o elimine elementos de la lista de patrones. </br> 

   ![Editar plantilla](../media/content-understanding/phone-template-live.png)</br>

4. Cuando finalice, haga clic en **Guardar**.
