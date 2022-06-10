---
title: Crear un tipo de información confidencial personalizada con PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Aprenda a crear e importar un tipo de información confidencial personalizada para directivas en el Centro de cumplimiento.
ms.openlocfilehash: 8678b7c218844d9963bd610b66e8b6c2c2647dea
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014528"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a>Crear un tipo de información confidencial personalizada con PowerShell

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En este artículo se muestra cómo crear un archivo de *paquete de reglas* XML que define [tipos de información confidencial](sensitive-information-type-entity-definitions.md) personalizados. En este artículo se describe un tipo de información confidencial personalizado que identifica un identificador de empleado. Puede usar el XML de ejemplo de este artículo como punto de partida para su propio archivo XML.

Para obtener más información sobre los tipos de información confidencial, consulte [Información sobre los tipos de información confidencial](sensitive-information-type-learn-about.md).

Después de crear un archivo XML bien formado, puede cargarlo en Microsoft 365 mediante PowerShell. A continuación, está listo para usar el tipo de información confidencial personalizada en las directivas. Puede probar su eficacia en la detección de la información confidencial según lo previsto.

> [!NOTE]
> Si no necesita el control específico que proporciona PowerShell, puede crear tipos de información confidencial personalizados en el portal de cumplimiento de Microsoft Purview. Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).

## <a name="important-disclaimer"></a>Declinación de responsabilidades importante

Soporte técnico de Microsoft no puede ayudarle a crear definiciones de coincidencia de contenido.

Para el desarrollo, las pruebas y la depuración personalizados de coincidencia de contenido, deberá usar sus propios recursos de TI internos o usar servicios de consultoría, como Microsoft Consulting Services (MCS). Soporte técnico de Microsoft ingenieros pueden proporcionar compatibilidad limitada con esta característica, pero no pueden garantizar que las sugerencias personalizadas de coincidencia de contenido satisfagan por completo sus necesidades.

MCS puede proporcionar expresiones regulares con fines de prueba. También pueden proporcionar ayuda para solucionar problemas de un patrón RegEx existente que no funciona según lo esperado con un solo ejemplo de contenido específico.

Consulte [Posibles problemas de validación que debe tener en cuenta](#potential-validation-issues-to-be-aware-of) en este artículo.

Para obtener más información sobre el motor Boost.RegEx (anteriormente conocido como RegEx++) que se usa para el procesamiento de texto, vea [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).

> [!NOTE]
> Si usa un carácter de y comercial (&) como parte de una palabra clave en el tipo de información confidencial personalizada, debe agregar un término adicional con espacios alrededor del carácter. Por ejemplo, use `L & P` _no_ `L&P`.

## <a name="sample-xml-of-a-rule-package"></a>XML de ejemplo de un paquete de reglas

Este es el XML de ejemplo del paquete de reglas que crearemos en este artículo. Los elementos y atributos se explican en las secciones siguientes.

```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
  <Version build="0" major="1" minor="0" revision="0"/>
  <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
  <Details defaultLangCode="en-us">
    <LocalizedDetails langcode="en-us">
      <PublisherName>Contoso</PublisherName>
      <Name>Employee ID Custom Rule Pack</Name>
      <Description>
      This rule package contains the custom Employee ID entity.
      </Description>
    </LocalizedDetails>
  </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
  <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="65">
      <IdMatch idRef="Regex_employee_id"/>
    </Pattern>
    <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
    </Pattern>
    <Pattern confidenceLevel="85">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
      <Any minMatches="1">
        <Match idRef="Keyword_badge" minCount="2"/>
        <Match idRef="Keyword_employee"/>
      </Any>
      <Any minMatches="0" maxMatches="0">
        <Match idRef="Keyword_false_positives_local"/>
        <Match idRef="Keyword_false_positives_intl"/>
      </Any>
    </Pattern>
  </Entity>
  <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
  <Keyword id="Keyword_employee">
    <Group matchStyle="word">
      <Term>Identification</Term>
      <Term>Contoso Employee</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_badge">
    <Group matchStyle="string">
      <Term>card</Term>
      <Term>badge</Term>
      <Term caseSensitive="true">ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_local">
    <Group matchStyle="word">
      <Term>credit card</Term>
      <Term>national ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_intl">
    <Group matchStyle="word">
      <Term>identity card</Term>
      <Term>national ID</Term>
      <Term>EU debit card</Term>
    </Group>
  </Keyword>
  <LocalizedStrings>
    <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
      <Name default="true" langcode="en-us">Employee ID</Name>
      <Description default="true" langcode="en-us">
      A custom classification for detecting Employee IDs.
      </Description>
      <Description default="false" langcode="de-de">
      Description for German locale.
      </Description>
    </Resource>
  </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a>¿Cuáles son sus requisitos clave? [Elementos Rule, Entity, Pattern]

Es importante que comprenda la estructura básica del esquema XML para una regla. Su comprensión de la estructura ayudará a su tipo de información confidencial personalizada a identificar el contenido correcto.

Una regla define una o varias entidades (también conocidas como tipos de información confidencial). Cada entidad define uno o varios patrones. Un patrón es lo que busca una directiva cuando evalúa el contenido (por ejemplo, el correo electrónico y los documentos).

En el marcado XML, "reglas" significan los patrones que definen el tipo de información confidencial. No asocie referencias a reglas de este artículo con "condiciones" o "acciones" comunes en otras características de Microsoft.

### <a name="simplest-scenario-entity-with-one-pattern"></a>Escenario más sencillo: entidad con un patrón

Este es un escenario sencillo: quiere que la directiva identifique el contenido que contiene identificadores de empleado de nueve dígitos que se usan en su organización. Un patrón hace referencia a la expresión regular de la regla que identifica números de nueve dígitos. Cualquier contenido que contenga un número de nueve dígitos satisface el patrón.

![Diagrama de entidad con un patrón.](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)

Sin embargo, este patrón podría identificar **cualquier** número de nueve dígitos, incluidos números más largos u otros tipos de números de nueve dígitos que no sean identificadores de empleado. Este tipo de coincidencia no deseada se conoce como *falso positivo*.

### <a name="more-common-scenario-entity-with-multiple-patterns"></a>Escenario más común: entidad con varios patrones

Debido a la posibilidad de falsos positivos, normalmente se usa más de un patrón para definir una entidad. Varios patrones proporcionan pruebas auxiliares para la entidad de destino. Por ejemplo, palabras clave, fechas u otro texto adicionales pueden ayudar a identificar la entidad original (por ejemplo, el número de empleado de nueve dígitos).

Por ejemplo, para aumentar la probabilidad de identificar el contenido que contiene un identificador de empleado, puede definir otros patrones para buscar:

- Patrón que identifica una fecha de contratación.
- Patrón que identifica una fecha de contratación y la palabra clave "employee ID".

![Diagrama de entidad con varios patrones.](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)

Hay puntos importantes que se deben tener en cuenta para varias coincidencias de patrones:

- Los patrones que requieren más pruebas tienen un nivel de confianza mayor. En función del nivel de confianza, puede realizar las siguientes acciones:
  - Use acciones más restrictivas (como el contenido en bloque) con coincidencias de mayor confianza.
  - Use acciones menos restrictivas (como enviar notificaciones) con coincidencias de menor confianza.

- `IdMatch` Los elementos auxiliares y `Match` hacen referencia a RegExes y palabras clave que en realidad son elementos secundarios del `Rule` elemento, no a `Pattern`. A estos elementos auxiliares se les hace referencia mediante , `Pattern`pero se incluyen en `Rule`. Este comportamiento significa que varias entidades y patrones pueden hacer referencia a una única definición de un elemento auxiliar, como una expresión regular o una lista de palabras clave.

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a>¿Qué entidad necesita identificar? [Elemento Entity, atributo ID]

Una entidad es un tipo de información confidencial (como un número de tarjeta de crédito) que tiene un patrón bien definido. Cada entidad tiene un GUID único como su id.

### <a name="name-the-entity-and-generate-its-guid"></a>Asignar un nombre a la entidad y generar su GUID

1. En el editor XML que prefiera, agregue los `Rules` elementos y `Entity` .
2. Agregue un comentario que contenga el nombre de la entidad personalizada, como Id. de empleado. Más adelante, agregará el nombre de la entidad a la sección de cadenas localizadas y ese nombre aparecerá en el Centro de administración al crear una directiva.
3. Genere un GUID único para la entidad. Por ejemplo, en Windows PowerShell, puede ejecutar el comando `[guid]::NewGuid()`. Más adelante, también agregará el GUID a la sección de cadenas localizadas de la entidad.

![Marcado XML que muestra elementos Rules y Entity.](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)

## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a>¿Qué patrón desea que coincida? [Elemento Pattern, elemento IdMatch, elemento Regex]

El patrón contiene la lista de lo que busca el tipo de información confidencial. El patrón puede incluir RegExes, palabras clave y funciones integradas. Las funciones realizan tareas como ejecutar RegExes para buscar fechas o direcciones. Los tipos de información confidencial pueden tener varios patrones con confianzas únicas.

En el diagrama siguiente, todos los patrones hacen referencia a la misma expresión regular. Este RegEx busca un número `(\d{9})` de nueve dígitos rodeado de espacio `(\s) ... (\s)`en blanco . El elemento hace referencia a `IdMatch` esta expresión regular y es el requisito común para todos los patrones que buscan la entidad Employee ID. `IdMatch` es el identificador que el patrón va a intentar hacer coincidir. Un `Pattern` elemento debe tener exactamente un `IdMatch` elemento.

![Marcado XML que muestra varios elementos Pattern que hacen referencia a un único elemento Regex.](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)

Una coincidencia de patrón satisfecho devuelve un nivel de recuento y confianza, que puede usar en las condiciones de la directiva. Al agregar una condición para detectar un tipo de información confidencial a una directiva, puede editar el nivel de recuento y confianza como se muestra en el diagrama siguiente. El nivel de confianza (también denominado precisión de coincidencia) se explica más adelante en este artículo.

![Opciones de precisión de coincidencia y recuento de instancias.](../media/sit-confidence-level.png)

Las expresiones regulares son eficaces, por lo que hay problemas que debe conocer. Por ejemplo, un RegEx que identifica demasiado contenido puede afectar al rendimiento. Para obtener más información sobre estos problemas, consulte la sección [Posibles problemas de validación que se deben tener en cuenta](#potential-validation-issues-to-be-aware-of) más adelante en este artículo.

## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a>¿Desea requerir pruebas adicionales? [Elemento Match, atributo minCount]

Además de `IdMatch`, un patrón puede usar el `Match` elemento para requerir pruebas auxiliares adicionales, como una palabra clave, RegEx, fecha o dirección.

Puede `Pattern` incluir varios `Match` elementos:

- Directamente en el `Pattern` elemento .
- Combinado mediante el uso del `Any` elemento .

`Match` los elementos están unidos por un operador AND implícito. En otras palabras, todos los `Match` elementos deben cumplirse para que el patrón coincida.

Puede usar el `Any` elemento para introducir operadores AND o OR. El `Any` elemento se describe más adelante en este artículo.

Puede usar el atributo opcional `minCount` para especificar cuántas instancias de una coincidencia deben encontrarse para cada `Match` elemento. Por ejemplo, puede especificar que se cumpla un patrón solo cuando se encuentren al menos dos palabras clave de una lista de palabras clave.

![Marcado XML que muestra el elemento Match con el atributo minOccurs.](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)

### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a>Palabras clave [elementos Keyword, Group y Term, atributos matchStyle y caseSensitive]

Como se describió anteriormente, la identificación de información confidencial a menudo requiere palabras clave adicionales como evidencia corroborativa. Por ejemplo, además de coincidir con un número de nueve dígitos, puede buscar palabras como "card", "badge" o "ID" mediante el elemento Keyword. El `Keyword` elemento tiene un `ID` atributo al que pueden hacer referencia varios `Match` elementos en varios patrones o entidades.

Las palabras clave se incluyen como una lista de elementos de `Term` un `Group` elemento. El `Group` elemento tiene un `matchStyle` atributo con dos valores posibles:

- **matchStyle="word"**: una coincidencia de palabras identifica palabras enteras rodeadas de espacios en blanco u otros delimitadores. Siempre debe usar **palabras** a menos que necesite hacer coincidir partes de palabras o palabras en idiomas asiáticos.

- **matchStyle="string"**: una coincidencia de cadena identifica las cadenas independientemente de lo que estén rodeadas. Por ejemplo, "ID" coincidirá con "bid" e "idea". Use `string` solo cuando necesite buscar coincidencias con palabras asiáticas o si la palabra clave podría incluirse en otras cadenas.

Por último, puede usar el `caseSensitive` atributo del `Term` elemento para especificar que el contenido debe coincidir exactamente con la palabra clave, incluidas las letras minúsculas y mayúsculas.

![Marcado XML que muestra elementos Match que hacen referencia a palabras clave.](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)

### <a name="regular-expressions-regex-element"></a>Expresiones regulares [elemento Regex]

En este ejemplo, la entidad employee `ID` ya usa el `IdMatch` elemento para hacer referencia a una expresión regular para el patrón: un número de nueve dígitos rodeado de espacios en blanco. Además, un patrón puede usar un `Match` elemento para hacer referencia a un elemento adicional `Regex` para identificar pruebas corroborativas, como un número de cinco o nueve dígitos en el formato de un código postal de EE. UU.

### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a>Patrones adicionales, como fechas o direcciones [funciones integradas]

Los tipos de información confidencial también pueden usar funciones integradas para identificar pruebas corroborantes. Por ejemplo, una fecha de EE. UU., una fecha de la UE, una fecha de expiración o una dirección de EE. UU. Microsoft 365 no admite la carga de sus propias funciones personalizadas. Sin embargo, al crear un tipo de información confidencial personalizado, la entidad puede hacer referencia a funciones integradas.

Por ejemplo, un distintivo de identificador de empleado tiene una fecha de contratación, por lo que esta entidad personalizada puede usar la función integrada `Func_us_date` para identificar una fecha en el formato que se usa normalmente en EE. UU.

Para obtener más información, vea [Funciones de tipo de información confidencial](sit-functions.md).

![Marcado XML que muestra el elemento Match que hace referencia a la función integrada.](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)

## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a>Diferentes combinaciones de pruebas [elemento Any, atributos minMatches y maxMatches]

En un `Pattern` elemento, todos los `IdMatch` elementos y `Match` están unidos por un operador AND implícito. En otras palabras, todas las coincidencias deben cumplirse antes de que se pueda cumplir el patrón.

Puede crear una lógica de coincidencia más flexible mediante el `Any` elemento para agrupar `Match` elementos. Por ejemplo, puede usar el `Any` elemento para que coincida con todos, ninguno o un subconjunto exacto de sus elementos secundarios `Match` .

El `Any` elemento tiene atributos opcionales `minMatches` y `maxMatches` que puede usar para definir cuántos de los elementos secundarios `Match` deben cumplirse antes de que se coincida con el patrón. Estos atributos definen el *número* de `Match` elementos, no el número de instancias de evidencia encontradas para las coincidencias. Para definir un número mínimo de instancias para una coincidencia específica, como dos palabras clave de una lista, use el `minCount` atributo para un `Match` elemento (consulte más arriba).

### <a name="match-at-least-one-child-match-element"></a>Coincidir como mínimo con un elemento Match secundario

Para requerir solo un número mínimo de `Match` elementos, puede usar el `minMatches` atributo . En efecto, estos `Match` elementos están unidos por un operador OR implícito. Este `Any` elemento se satisface si se encuentra una fecha con formato EE. UU. o una palabra clave de cualquiera de las listas.

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```

### <a name="match-an-exact-subset-of-any-children-match-elements"></a>Coincidir un subconjunto exacto de elementos Match secundarios

Para requerir un número exacto de `Match` elementos, establezca `minMatches` y `maxMatches` en el mismo valor. Este `Any` elemento solo se satisface si se encuentra exactamente una fecha o palabra clave. Si hay más coincidencias, el patrón no coincide.

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```

### <a name="match-none-of-children-match-elements"></a>Ninguna coincidencia de elementos Match secundarios

Si quiere exigir la ausencia de pruebas específicas para que se cumpla un patrón, puede establecer los atributos minMatches y maxMatches en 0. Esto puede resultar útil si tiene una lista de palabras clave u otras pruebas que es probable que indiquen un falso positivo.

Por ejemplo, la entidad Id. de empleado busca la palabra clave "tarjeta", ya que puede hacer referencia a una "tarjeta de identificación". Pero, si la palabra "tarjeta" solo aparece en la frase "tarjeta de crédito", es poco probable que "tarjeta" en este contenido signifique "tarjeta de identificación". Por lo tanto, puede agregar "tarjeta de crédito" con una palabra clave a una lista de términos que quiera excluir para impedir que se cumpla el patrón.

```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a>Coincidencia de varios términos únicos

Si quiere hacer coincidir una serie de condiciones únicas, utilice el parámetro *uniqueResults*, establecido en *true*, como se muestra en el siguiente ejemplo:

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

En este ejemplo, se define un patrón para la revisión del salario con al menos tres coincidencias únicas.

## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a>¿Cuál es la proximidad con que la entidad tiene que aparecer junto a otra prueba? [Atributo patternsProximity]

El tipo de información confidencial busca un patrón que represente un id. de empleado y, como parte de ese patrón, también busca pruebas corroboradoras, como una palabra clave (por ejemplo, "id."). Cuanto más cerca se encuentre esta prueba, más probable es que el patrón sea el id. de empleado adecuado. Puede determinar la proximidad de otras pruebas en el patrón con la entidad mediante el atributo patternsProximity obligatorio del elemento Entity.

![Marcado XML que muestra el atributo patternsProximity.](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)

Por cada patrón en la entidad, el valor del atributo patternsProximity define la distancia (en caracteres Unicode) desde la ubicación de IdMatch para el resto de las coincidencias especificadas para ese patrón. La ventana de proximidad se ancla mediante la ubicación IdMatch, con la ventana extendiéndose hacia la izquierda y la derecha de la ubicación IdMatch.

![Diagrama de la ventana de proximidad.](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)

En el ejemplo siguiente, se muestra cómo la ventana de proximidad afecta a la coincidencia de patrones donde el elemento IdMatch de la entidad personalizada "Id. de empleado" exige como mínimo una coincidencia corroboradora de una palabra clave o fecha. Solo ID1 coincide porque, en el caso de ID2 e ID3, en la ventana de proximidad no se encuentra ninguna prueba corroboradora, o bien se encuentra una parcial.

![Diagrama de evidencia corroborativa y ventana de proximidad.](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Tenga en cuenta que, para el correo electrónico, el cuerpo del mensaje y cada dato adjunto se tratan como elementos independientes. Esto significa que la ventana de proximidad no se extiende más allá del final de cada uno de estos elementos. Para cada elemento (datos adjuntos o cuerpo), tanto el idMatch como la evidencia corroborativa deben residir en ese elemento.

## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a>¿Cuáles son los niveles de confianza adecuados para diferentes patrones? [Atributo confidenceLevel, atributo recommendedConfidence]

Cuantas más pruebas necesite un patrón, más seguro estará de que se haya identificado una entidad real (como un id. de empleado) cuando coincida el patrón. Por ejemplo, tendrá más confianza en un patrón que necesite un número de identificación de nueve dígitos, una fecha de contratación y una palabra clave a muy poca distancia, que en un patrón que solo necesite un número de identificación de nueve dígitos.

El elemento Pattern tiene un atributo confidenceLevel obligatorio. Piense en el valor de confidenceLevel (un número entero entre 1 y 100) como un id. único para cada patrón de una entidad (los patrones de una entidad deben tener asignados distintos niveles de confianza). El valor preciso del número entero no importa: solo tiene que elegir números que tengan sentido para el equipo de cumplimiento. Después de cargar el tipo de información confidencial personalizado y crear una directiva, puede hacer referencia a esos niveles de confianza en las condiciones de las reglas que cree.

![Marcado XML que muestra elementos Pattern con valores diferentes para el atributo confidenceLevel.](../media/sit-xml-markedup-2.png)

Además del atributo confidenceLevel de cada elemento Pattern, el elemento Entity tiene un atributo recommendedConfidence. El atributo de confianza recomendada puede considerarse como el nivel de confianza predeterminado de la regla. Cuando se crea una regla en una directiva, si no se especifica el uso de un nivel de confianza para la regla, buscará coincidencias en función del nivel de confianza recomendado para la entidad. Tenga en cuenta que el atributo recommendedConfidence es obligatorio para cada identificador de entidad en el paquete de reglas, si no está, no podrá guardar directivas que usen el tipo de Información confidencial.

## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a>¿Quiere admitir otros idiomas en la interfaz de usuario del Centro de seguridad y cumplimiento? [Elemento LocalizedStrings]

Si el equipo de cumplimiento usa el portal de cumplimiento de Microsoft Purview para crear directivas en diferentes configuraciones regionales y en diferentes idiomas, puede proporcionar versiones localizadas del nombre y la descripción del tipo de información confidencial personalizada. Cuando el equipo de cumplimiento use Microsoft 365 en un idioma compatible, verá el nombre localizado en la interfaz de usuario.

![Recuento de instancias y configuración de precisión de coincidencia.](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

El elemento Rules necesita contener un elemento LocalizedStrings, que contiene un elemento Resource que hace referencia al GUID de la entidad personalizada. A su vez, cada elemento Resource contiene uno o más elementos Name y Description, y cada uno usa el atributo langcode para especificar una cadena localizada para un idioma específico.

![Marcado XML que muestra el contenido del elemento LocalizedStrings.](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)

Tenga en cuenta que las cadenas localizadas solo se usan para mostrar el tipo de información confidencial personalizado en la interfaz de usuario del Centro de cumplimiento. No se pueden usar cadenas localizadas para proporcionar otras versiones localizadas de una lista de palabras clave o una expresión regular.

## <a name="other-rule-package-markup-rulepack-guid"></a>Otro marcado de paquete de reglas [GUID de RulePack]

Por último, el principio de cada elemento RulePackage contiene información general que necesita rellenar. Puede usar el siguiente marcado como una plantilla y reemplazar los marcadores de posición "…" con su propia información.

Aún más importante, necesita generar un GUID para el elemento RulePack. Anteriormente, ha generado un GUID para la entidad (se trata de un GUID secundario para el elemento RulePack). Hay varias formas de generar GUID, pero puede hacerlo fácilmente en PowerShell si escribe lo siguiente: [guid]::NewGuid().

El elemento Versión también es importante. Al cargar por primera vez un paquete de reglas, Microsoft 365 anota el número de versión. Si posteriormente actualiza el paquete de reglas y carga una nueva versión, asegúrese de actualizar el número de versión (de lo contrario, Microsoft 365 no implementará el paquete de reglas).

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." />
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
  . . .
 </Rules>
</RulePackage>
```

Una vez completado, el elemento RulePack será parecido a este.

![Marcado XML que muestra el elemento RulePack.](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)

## <a name="validators"></a>Validadores

Microsoft 365 expone procesadores de funciones para SIT de uso común como validadores. Esta es una lista de ellos.

### <a name="list-of-currently-available-validators"></a>Lista de validadores disponibles actualmente

- `Func_credit_card`
- `Func_ssn`
- `Func_unformatted_ssn`
- `Func_randomized_formatted_ssn`
- `Func_randomized_unformatted_ssn`
- `Func_aba_routing`
- `Func_south_africa_identification_number`
- `Func_brazil_cpf`
- `Func_iban`
- `Func_brazil_cnpj`
- `Func_swedish_national_identifier`
- `Func_india_aadhaar`
- `Func_uk_nhs_number`
- `Func_Turkish_National_Id`
- `Func_australian_tax_file_number`
- `Func_usa_uk_passport`
- `Func_canadian_sin`
- `Func_formatted_itin`
- `Func_unformatted_itin`
- `Func_dea_number_v2`
- `Func_dea_number`
- `Func_japanese_my_number_personal`
- `Func_japanese_my_number_corporate`

Esto le ofrece la capacidad de definir sus propios RegEx y validarlos. Para usar validadores, defina su propio RegEx y use la `Validator` propiedad para agregar el procesador de funciones de su elección. Una vez definido, puede usar este RegEx en una SIT.

En el ejemplo siguiente, se define una expresión regular - Regex_credit_card_AdditionalDelimiters para la tarjeta de crédito, que luego se valida mediante la función de suma de comprobación de la tarjeta de crédito mediante Func_credit_card como validador.

```xml
<Regex id="Regex_credit_card_AdditionalDelimiters" validators="Func_credit_card"> (?:^|[\s,;\:\(\)\[\]"'])([0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4})(?:$|[\s,;\:\(\)\[\]"'])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_credit_card_AdditionalDelimiters" />
<Any minMatches="1">
<Match idRef="Keyword_cc_verification" />
<Match idRef="Keyword_cc_name" />
<Match idRef="Func_expiration_date" />
</Any>
</Pattern>
</Entity>
```

Microsoft 365 proporciona dos validadores genéricos

### <a name="checksum-validator"></a>Validador de suma de comprobación

En este ejemplo, se define un validador de suma de comprobación para el identificador de empleado para validar el RegEx para EmployeeID.

```xml
<Validators id="EmployeeIDChecksumValidator">
<Validator type="Checksum">
<Param name="Weights">2, 2, 2, 2, 2, 1</Param>
<Param name="Mod">28</Param>
<Param name="CheckDigit">2</Param> <!-- Check 2nd digit -->
<Param name="AllowAlphabets">1</Param> <!— 0 if no Alphabets -->
</Validator>
</Validators>
<Regex id="Regex_EmployeeID" validators="ChecksumValidator">(\d{5}[A-Z])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_EmployeeID"/>
</Pattern>
</Entity>
```

### <a name="date-validator"></a>Validador de fecha

En este ejemplo, se define un validador de fecha para una parte RegEx de la que es date.

```xml
<Validators id="date_validator_1"> <Validator type="DateSimple"> <Param name="Pattern">DDMMYYYY</Param> <!—supported patterns DDMMYYYY, MMDDYYYY, YYYYDDMM, YYYYMMDD, DDMMYYYY, DDMMYY, MMDDYY, YYDDMM, YYMMDD --> </Validator> </Validators>
<Regex id="date_regex_1" validators="date_validator_1">\d{8}</Regex>
```

## <a name="changes-for-exchange-online"></a>Cambios para Exchange Online

Antes se podía usar PowerShell de Exchange Online para importar tipos de información confidencial personalizados para DLP. Ahora los tipos de información confidencial personalizados se pueden usar tanto en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a> como en el Centro de cumplimiento. Como parte de esta mejora, debe usar Security & Compliance PowerShell para importar los tipos de información confidencial personalizados; ya no puede importarlos desde Exchange Online PowerShell. Los tipos de información confidencial personalizados seguirán funcionando como hasta ahora, pero los cambios realizados en los tipos de información confidencial personalizados en el Centro de cumplimiento pueden tardar hasta una hora en mostrarse en el Centro de administración de Exchange.

Tenga en cuenta que, en el Centro de seguridad y cumplimiento, se usa el cmdlet **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** para cargar un paquete de reglas (anteriormente, en el Centro de administración de Exchange, se usaba el cmdlet ClassificationRuleCollection). (Antes, en el Centro de administración de Exchange, usó el cmdlet **ClassificationRuleCollection**).

## <a name="upload-your-rule-package"></a>Cargar un paquete de reglas

Para cargar un paquete de reglas, siga este procedimiento:

1. Guárdelo como un archivo .xml con codificación Unicode.

2. [Conectarse a Security & Compliance PowerShell](/powershell/exchange/exchange-online-powershell)

3. Utilice la sintaxis siguiente:

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('PathToUnicodeXMLFile'))
   ```

   En este ejemplo se carga el archivo XML de Unicode denominado MyNewRulePack.xml desde C:\Mis documentos.

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('C:\My Documents\MyNewRulePack.xml'))
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).

   > [!NOTE]
   > El número máximo de paquetes de reglas admitidos es 10, pero cada paquete puede contener la definición de varios tipos de información confidencial.

4. Para comprobar si un tipo de información confidencial se creó correctamente, siga uno de estos procedimientos:

   - Ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) para comprobar que se muestra el nuevo paquete de reglas en la lista:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Ejecute el cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para comprobar que se muestra el tipo de información confidencial:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     Para los tipos personalizados de información confidencial, el valor de propiedad de Publisher no será Microsoft Corporation, sino otro.

   - Reemplace \<Name\> con el valor de Nombre del tipo de información confidencial (por ejemplo, Id. de empleado) y ejecute el cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype):

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="potential-validation-issues-to-be-aware-of"></a>Posibles problemas de validación

Al cargar un archivo XML de paquete de reglas, el sistema valida el código XML y comprueba si hay patrones incorrectos conocidos y problemas de rendimiento obvios. Estos son algunos de los problemas conocidos (la validación comprueba las expresiones regulares):

- Las aserciones de apariencia en la expresión regular solo deben tener una longitud fija. Las aserciones de longitud variable producirán errores.

  Por ejemplo, `"(?<=^|\s|_)"` no pasará la validación. El primer patrón (`^`) es de longitud cero, mientras que los dos patrones siguientes (`\s` y `_`) tienen una longitud de uno. Una manera alternativa de escribir esta expresión regular es `"(?:^|(?<=\s|_))"`.

- No se puede comenzar o terminar con alternador `|`, que coincide con todo porque se considera una coincidencia vacía.

  Por ejemplo, `|a` o `b|` no pasará la validación.

- No se puede comenzar o terminar con un `.{0,m}` patrón, que no tiene ningún propósito funcional y solo afecta al rendimiento.

  Por ejemplo, `.{0,50}ASDF` o `ASDF.{0,50}` no pasará la validación.

- No se puede tener `.{0,m}` o `.{1,m}` en grupos y no se puede tener `.\*` o `.+` en grupos.

  Por ejemplo, `(.{0,50000})` no pasará la validación.

- No se puede tener ningún carácter con `{0,m}` o `{1,m}` repetidores en grupos.

  Por ejemplo, `(a\*)` no pasará la validación.

- No se puede comenzar o terminar con `.{1,m}`; en su lugar, use `.`.

  Por ejemplo, `.{1,m}asdf` no pasará la validación. En su lugar, use `.asdf`.

- No se puede tener un repetidor sin enlazar (como `*` o `+`) en un grupo.

  Por ejemplo, `(xx)\*` y `(xx)+` no pasará la validación.

- Las contraseñas pueden tener 50 caracteres de longitud como máximo.  Si tiene una palabra clave dentro de un grupo que supere esto, una solución sugerida es crear el grupo de términos como un [diccionario de palabras clave](./create-a-keyword-dictionary.md) y hacer referencia al GUID del diccionario de palabras clave en la estructura XML como parte de la entidad para Match o idMatch en el archivo.

- Cada tipo de información confidencial personalizado puede tener un máximo de 2048 palabras clave total.

- El tamaño máximo de los diccionarios de palabras clave en un solo inquilino es de 480 KB comprimidos para cumplir con los límites del esquema de AD. Haga referencia al mismo diccionario tantas veces como sea necesario al crear tipos de información confidencial personalizados. Comience con la creación de listas de palabras clave personalizadas en el tipo de información confidencial y use diccionarios de palabras clave si tiene más de 2048 palabras clave en una lista de palabras clave o una palabra clave tiene más de 50 caracteres de longitud.

- En un espacio empresarial se permite un máximo de 50 tipos de información confidencial basada en diccionario de palabras clave.

- Asegúrese de que cada elemento de entidad contiene un atributo recommendedConfidence.

- Cuando se usa el cmdlet de PowerShell, hay un tamaño máximo devuelto de los datos deserializados de aproximadamente 1 megabyte.   Esto afectará al tamaño del archivo XML del paquete de reglas. Mantenga el archivo cargado limitado a un máximo de 770 megabytes como límite sugerido para obtener resultados coherentes sin errores al procesarlo.

- La estructura XML no requiere caracteres de formato como espacios, tabulaciones o entradas de retorno de carro o avance de línea.  Anote esto al optimizar espacio en las cargas. Las herramientas como el código del elemento visual de Microsoft ofrecen características de línea de combinación para compactar el archivo XML.

Si un tipo personalizado de información confidencial contiene un problema que puede afectar al rendimiento, no se cargará y es posible que se muestre uno de estos mensajes de error:

- `Generic quantifiers which match more content than expected (e.g., '+', '*')`

- `Lookaround assertions`

- `Complex grouping in conjunction with general quantifiers`

## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a>Volver a rastrear el contenido para identificar la información confidencial

Microsoft 365 usa el rastreador de búsqueda para identificar y clasificar información confidencial en el contenido del sitio. El contenido en los sitios de OneDrive para la Empresa y SharePoint Online se vuelve a rastrear automáticamente cada vez que se actualiza. Pero, para identificar el nuevo tipo de información confidencial personalizado en todo el contenido existente, es necesario volver a rastrear ese contenido.

En Microsoft 365, no se puede solicitar manualmente una recrawl de toda una organización, pero puede solicitar manualmente una recrawl para una colección de sitios, una lista o una biblioteca. Para obtener más información, vea [Solicitud manual de rastreo y reindexación de un sitio, una biblioteca o una lista](/sharepoint/crawl-site-content).

## <a name="reference-rule-package-xml-schema-definition"></a>Referencia: Definición de esquema XML de paquete de reglas

Puede copiar este marcado, guardarlo como un archivo XSD y usarlo para validar el archivo XML del paquete de reglas.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a>Más información

- [Información sobre la prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Funciones de tipo de información confidencial](sit-functions.md)
