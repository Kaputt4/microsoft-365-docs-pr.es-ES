---
title: Referencia de filtros de tipo de información confidencial personalizada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: En este artículo se presenta una lista de los filtros que se pueden codificar en tipos de información confidencial personalizados.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322968"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>Referencia de filtros de tipo de información confidencial personalizada

En Microsoft puede definir filtros o comprobaciones adicionales al crear un tipo de información confidencial personalizado (SIT).

## <a name="list-of-supported-filters-and-use-cases"></a>Lista de filtros admitidos y casos de uso

### <a name="alldigitssame-exclude"></a>AllDigitsSame Exclude

Descripción: permite excluir coincidencias que tienen todos los dígitos como dígitos duplicados, como 111111111 o 111-111-111

Definición de filtros
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

Usarlo en el paquete de reglas en el nivel de entidad
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

Usarlo en el paquete de reglas en el nivel de patrón
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

Descripción: permite definir los caracteres iniciales de la entidad. Tiene dos variantes, incluir y excluir.

Por ejemplo, para excluir los números a partir de 0500, 91, 091, 010 en una lista como esta:

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

puede usar este xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
Por ejemplo, para incluir los números a partir de 0500, 91, 091, 0100 en una lista como esta: 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

puede usar este xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

Descripción: permite definir los caracteres finales de la entidad. 

Por ejemplo, para excluir los números que terminan con 0500,91.091, 0100 en una lista como esta:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

puede usar este xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

Por ejemplo, para incluir los números que terminan con 0500, 91, 091, 0100, en una lista como esta:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

puede usar este xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

Descripción: permite prohibir determinadas coincidencias para evitar que activen la regla. Por ejemplo, excluya 4111111111111 de la lista de coincidencias válidas de tarjetas de crédito.

Por ejemplo, para excluir números de tarjeta de crédito como 4111111111111111111 y 3241891031111111 en una lista como esta:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

puede usar este xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

Por ejemplo, para incluir números de tarjeta de crédito como 4111111111111111111 y 3241891031111111 en una lista como esta:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

puede usar este xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>Prefijo TextMatchFilter

Descripción: permite definir los caracteres anteriores que deben incluirse o excluirse siempre. Por ejemplo, si el número de tarjeta de crédito está precedido por "Id. de pedido:", quita la coincidencia de las coincidencias válidas.

Por ejemplo, para excluir las repeticiones de números de teléfono que **tienen Teléfono número** y **llamarme** en cadenas antes del número de teléfono, en una lista como esta:

- número de teléfono 091-8974-653278
- Teléfono 45-124576532-123
- 45-124576532-123

puede usar este xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

Por ejemplo, para incluir  repeticiones que tienen cadenas de tarjeta de crédito y **#tarjeta** antes del número de tarjeta de crédito, en una lista como esta:

- Tarjeta de crédito 45-124576532-123 
- 45-124576532-123 (que podría ser número de teléfono)

puede usar este xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a>Sufijo TextMatchFilter

Descripción: permite definir los siguientes caracteres que deben incluirse o excluirse siempre. Por ejemplo, si el número de tarjeta de crédito va seguido de '/xuid', quite la coincidencia de las coincidencias válidas.

Por ejemplo, las repeticiones de exclusión superior si hay 5 instancias más de cuatro dígitos como sufijo en una lista como esta:

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

puede usar este xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
Por ejemplo, para excluir repeticiones si se siguen por **/xuidsuffix**, como una de esta lista:

- 1234-5678-9321 /xuid
- 1234-5678-9321

puede usar este xml

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a>Uso de filtros en paquetes de reglas

Los filtros se pueden definir en el SIT completo o en un patrón. Estos son algunos ejemplos de fragmentos de código. 

### <a name="at-sensitive-information-type-level"></a>En el nivel de tipo de información confidencial

Filters at Entity: cubrirá todos los patrones secundarios

Los filtros se aplicarán en **todas las** instancias clasificadas por cualquiera de los patrones de esa entidad o tipo confidencial

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>En el patrón individual del nivel de tipo de información confidencial

Filtra solo en el nivel de patrón.

El filtro se aplicará en las instancias coincidentes con el patrón.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>En el nivel de tipo de información confidencial y un filtro adicional en algunos de los patrones de esa entidad

Filtros en entidad + patrón

Los filtros se aplicarán en **todas las** instancias clasificadas por cualquiera de los patrones de esa entidad o tipo confidencial. El filtro de nivel de patrón filtrará las instancias coincidentes con ese patrón.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>Más información

- [Obtenga más información acerca de la prevención de pérdida de datos](dlp-learn-about-dlp.md)

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)

- [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md)
