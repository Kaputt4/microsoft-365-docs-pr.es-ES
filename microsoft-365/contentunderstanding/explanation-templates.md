---
title: Uso de plantillas de explicación en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga más información sobre cómo usar y guardar plantillas de explicación en Microsoft Syntex.
ms.openlocfilehash: ef1e3cd3575d5e943c2ea39e98f7c85046de32ec
ms.sourcegitcommit: ca082da1c51a3f643f152492579eef5679d52bd0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68547760"
---
# <a name="use-explanation-templates-in-microsoft-syntex"></a>Uso de plantillas de explicación en Microsoft Syntex

Aunque se pueden agregar manualmente varios valores de la lista de frases para la explicación, puede resultar más fácil usar las plantillas que se le proporcionan en la biblioteca de explicación.

Por ejemplo, en lugar de añadir manualmente todas las variaciones para *fecha*, puede utilizar la plantilla de la lista de frases para *fecha* que ya incluye una serie de valores de la lista de frases:

![Biblioteca de explicación.](../media/content-understanding/explanation-template.png)

La biblioteca de explicación incluye varias explicaciones de la *lista de frases* más utilizadas, entre las que se incluyen:

- Fecha: fechas del calendario, todos los formatos. Incluye texto y números (por ejemplo, "9 de diciembre de 2020").
- Fecha (numérica): fechas del calendario, todos los formatos. Incluye números (por ejemplo, 1-11-2020).
- Hora: formatos de 12 y 24 horas.
- Número: números positivos y negativos, hasta 2 decimales.
- Porcentaje: una lista de patrones que representan un porcentaje. Por ejemplo, 1 %, 11 %, 100 % o 11,11 %.
- Número de teléfono: formatos comunes de EE. UU. e internacionales. Por ejemplo, 000 000 0000, 000-000-0000, (000)000-0000 o (000) 000-0000.
- Código postal: formatos de código postal de Estados Unidos. Por ejemplo, 11111, 11111-1111.
- Primera palabra de una frase: patrones comunes para palabras de hasta nueve caracteres.
- Final de una oración: signos de puntuación comunes para el final de una oración
- Tarjeta de crédito: formatos de número de tarjeta de crédito comunes. Por ejemplo, 1111-1111-1111-1111.
- Número de la seguridad social: formato de número del seguro social de EE. UU. Por ejemplo, 111-11-1111.
- Casilla: una lista de frases que representa variaciones en una casilla rellenada. Por ejemplo, _X_, _ _X_.
- Moneda: principales símbolos internacionales. Por ejemplo: .$
- Correo electrónico CC: lista de frases con el término "CC:" que se suele encontrar cerca de los nombres o direcciones de correo electrónico de otras personas o grupos a los que se envió el mensaje.
- Fecha del correo electrónico: lista de frases con el término "Enviado el:", que se suele encontrar cerca de la fecha en que se envió el correo electrónico.
- Saludo de correo electrónico: líneas de apertura comunes de los correos electrónicos.
- Destinatario de correo electrónico: lista de frases con el término "Para:", que a menudo se encuentra cerca de los nombres o direcciones de correo electrónico de personas o grupos a los que se envió el mensaje.
- Remitente de correo electrónico: lista de frases con el término "De:" que se suele encontrar cerca del nombre o la dirección de correo del remitente.
- Asunto del correo electrónico: lista de frases con el término "Asunto:" que se suele encontrar cerca del asunto del correo electrónico.

La biblioteca de explicación incluye varias explicaciones de *expresiones regulares* frecuentemente utilizadas, entre ellas:

- Números de 6 a 17 dígitos: coincide con cualquier número de 6 a 17 dígitos de longitud. Los números de cuenta bancaria de EE. UU. se ajustan a este patrón.
- Correo electrónico: coincide con un tipo común de dirección de correo electrónico como meganb@contoso.com
- Número de identificación fiscal de los EE. UU.: coincide con un número de tres dígitos que empieza por nueve seguido de un número de seis dígitos que empieza por siete u ocho.
- Dirección web (URL): coincide con el formato de una dirección web que empieza por http:// o https://.

La biblioteca de explicación también incluye tres tipos de plantillas automáticas que funcionan con los datos que ha etiquetado en los archivos de ejemplo:

- Después de la etiqueta: las palabras o caracteres que aparecen después de las etiquetas en los archivos de ejemplo.
- Antes de la etiqueta: las palabras o caracteres que aparecen antes de las etiquetas en los archivos de ejemplo.
- Etiquetas: hasta las 10 primeras etiquetas de los archivos de ejemplo.

Para ilustrar cómo funcionan las plantillas automáticas, en el siguiente archivo de ejemplo usaremos la plantilla de explicación Antes de la etiqueta para dar más información al modelo y obtener una coincidencia más precisa.

![Archivo de ejemplo.](../media/content-understanding/before-label.png)

Al seleccionar la plantilla de explicación Antes de la etiqueta, buscará el primer conjunto de palabras que aparezca antes de la etiqueta en los archivos de ejemplo. En el ejemplo, el conjunto de palabras que se identifican en el primer archivo de ejemplo es "A partir de".

![Plantilla Antes de la etiqueta.](../media/content-understanding/before-label-explanation.png)

Puede seleccionar **Agregar** para crear una explicación a partir de la plantilla. A medida que agregue más archivos de ejemplo, se identificarán y agregarán palabras adicionales a la lista de frases.

![Agregar la etiqueta.](../media/content-understanding/before-label-add.png)

## <a name="use-a-template-from-the-explanation-library"></a>Uso de una plantilla de la biblioteca de explicaciones

1. En la sección de **Explicaciones** de la página de **Entrenamiento** de su modelo, seleccione **Nueva** y luego **De una plantilla**.

   ![Agregar Antes de etiqueta.](../media/content-understanding/from-template.png)

2.  En la página **Plantillas de explicación**, seleccione la explicación que desee usar y seleccione **Agregar**.

    ![Seleccione una plantilla.](../media/content-understanding/phone-template.png)

3. La información de la plantilla que ha seleccionado se mostrará en la página **Crear una explicación**. Si es necesario, edite el nombre de la explicación y agregue o elimine elementos de la lista de frases.

    ![Editar plantilla.](../media/content-understanding/phone-template-live.png)

4. Cuando finalice, haga clic en **Guardar**.

## <a name="save-a-template-to-the-explanation-library"></a>Guardar una plantilla en la biblioteca de explicaciones

Puede guardar una explicación como plantilla para que esté disponible en la biblioteca de explicaciones de un centro de contenido que se usará con otros modelos. La plantilla incluirá la configuración básica y avanzada para la explicación, con la excepción de la opción de indicar dónde aparecen las frases en un documento.

> [!NOTE]
> Solo se pueden guardar como plantilla las explicaciones de la lista de frases y las expresiones regulares.

1. En la sección **Explicaciones** de la página **Entrenamiento** del modelo:

   a. En la lista de explicaciones, seleccione la que quiere guardar como plantilla.

   b. Seleccione **Guardar como plantilla**.

    ![Captura de pantalla de la sección Explicaciones que muestra la opción Guardar como plantilla.](../media/content-understanding/explanation-save-as-template.png)

2. En la página **Guardar plantilla de explicación**:

   a. En la sección **Nombre**, cambie el nombre de la explicación si es necesario.

   b. En la sección **Descripción**, agregue una descripción para que otros usuarios sepan cómo usar la explicación.

   c. Seleccione **Guardar**.

    ![Captura de pantalla de la página Guardar plantilla de explicación.](../media/content-understanding/save-explanation-template.png)

### <a name="see-also"></a>Ver también

[Tipos de explicación en Microsoft Syntex](explanation-types-overview.md)