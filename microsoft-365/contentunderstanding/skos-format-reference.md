---
title: Referencia de formato SKOS para la taxonomía de SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: high
description: Obtenga información sobre la referencia de formato SKOS para la taxonomía de SharePoint.
ms.openlocfilehash: 794b1d444ca49a7b33e0a60b46cefe896dd8578a
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564200"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Referencia de formato SKOS para la taxonomía de SharePoint

Este artículo incluye el vocabulario de RDF usado para representar la [taxonomía de SharePoint](/dotnet/api/microsoft.sharepoint.taxonomy) y se basa en [SKOS](https://www.w3.org/TR/skos-primer/). Para serializar esta sintaxis RDF, utilice RDF [TURTLE](https://www.w3.org/TR/turtle/).

En la tabla siguiente se muestran los equivalentes de [SKOS](https://www.w3.org/TR/skos-primer/) para el vocabulario de la [taxonomía de SharePoint](/dotnet/api/microsoft.sharepoint.taxonomy). SharePoint no admite valores [de SKOS](https://www.w3.org/TR/skos-primer/) que no tengan equivalente de taxonomía de SharePoint.

|Taxonomía de SharePoint|Equivalente de SKOS|
|:-----------------|:--------------|
|sharepoint-taxonomy: término|skos: Concepto|
|sharepoint-taxonomy: TermSet|skos: ConceptScheme|
|sharepoint-taxonomy: inTermSet|skos: inScheme|
|sharepoint-taxonomy: hasTopLevelTerm|skos: hasTopConcept|
|sharepoint-taxonomy: topLevelTermOf|skos: topConceptOf|
|sharepoint-taxonomy: defaultLabel|skos: prefLabel|
|sharepoint-taxonomy: termSetName|skos: prefLabel|
|sharepoint-taxonomy: propertyName|skos: prefLabel|
|sharepoint-taxonomy: otherLabel|skos: altLabel|
|sharepoint-taxonomy: description|skos: definición|
|sharepoint-taxonomy: parent|skos: más amplio|
|sharepoint-taxonomy: secundario|skos: más estrecho|

En la tabla siguiente se muestran las entidades del vocabulario de la taxonomía de SharePoint derivados de [OWL](https://www.w3.org/TR/owl2-primer/).

|Vocabulario de la taxonomía de SharePoint|Derivado de OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy: isAvailableForTagging|owl: datatypeproperty|
|sharepoint-taxonomy: SharedCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-taxonomy: LocalCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-taxonomy: CustomPropertyForTermSet|owl: ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabulario de la taxonomía de SharePoint

A taxonomy is a formal classification system. A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.

**sharepoint-taxonomy:Term**

Representa un término o una palabra clave en una jerarquía de metadatos administrados.

Un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) es la unidad atómica de un [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) de SharePoint. Cada [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenece a un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertenece a un [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group).

La sintaxis para definir un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) es la siguiente:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Obligatoriamente, existe un [término](/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel es el nombre del [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) tal y como aparece en la representación visual. Los campos obligatorios para definir un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) incluyen:

- sharepoint-taxonomy: defaultLabel
- sharepoint-taxonomy: inTermSet

Un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) puede:

- Estar relacionado jerárquicamente con otro [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term), siempre y cuando ambos [Términos](/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenezcan al mismo [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tener varios [Términos](/dotnet/api/microsoft.sharepoint.taxonomy.term) secundarios, pero un único [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) principal.
- No tiene un [term](/dotnet/api/microsoft.sharepoint.taxonomy.term) primario definido, si es un topLevelTermOf un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tener una única defaultLabel por idioma de trabajo de [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).
- No existir en caso de que no contenga un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) principal y de que no sea el término de nivel superior (topLevelTermOf) de un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tener una única defaultLabel en el mismo nivel jerárquico.

**sharepoint-taxonomy:TermSet**

Representa un conjunto jerárquico o plano de objetos Term denominado "TermSet".

Como el nombre sugiere, TermSet es un conjunto de [Términos](/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) debe pertenecer a un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Ningún [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) puede existir de manera independiente.

La sintaxis para definir un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) es la siguiente:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

Los [TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) se agrupan lógicamente en [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group). El campo obligatorio para definir un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) es el siguiente:

- sharepoint-taxonomy: termSetName

Si el termSetName proporcionado no es único dentro de [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint anexa un número al final del nombre para mantener la exclusividad de termSetName(s).

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint usa esta propiedad para asignar el [término](/dotnet/api/microsoft.sharepoint.taxonomy.term) más alto del [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), que es el punto de entrada a la jerarquía de [Términos](/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Se trata de una relación inversa con la taxonomía de sharepoint: topLevelTermOf.

La sintaxis para definirlo es la siguiente:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> No se puede definir el [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) principal.

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy: topLevelTermOf es el inverso de sharepoint-taxonomy: hasTopLevelTerm

La sintaxis para definirlo es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Use esto para asignar un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) a un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) solo puede existir en un único [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint requiere esta propiedad a la hora de [definir un término](#sharepoint-taxonomy-vocabulary).

## <a name="required-labels"></a>Etiquetas necesarias

Antes de que usted empiece a usar metadatos administrados, resulta conveniente que su organización planifique cuidadosamente. La cantidad de planificación que debe llevar a cabo dependerá del grado de formalidad de su taxonomía. Asimismo, dependerá de la cantidad de control que desee aplicar a los metadatos. En cada nivel de la jerarquía, tiene que configurar las etiquetas obligatorias para un término o TermSet.

Un término puede tener una o más etiquetas en el idioma predeterminado, y ninguna, una o varias etiquetas en el idioma no predeterminado. Si el término tiene etiquetas en un idioma, una de ellas debe ser la etiqueta predeterminada.

**sharepoint-taxonomy:defaultLabel**

Use this default lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). Use to visually representing the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir una defaultLabel (etiqueta predeterminada) es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

La DefaultLabel contiene dos partes: la cadena y la etiqueta de idioma. El idioma debe ser uno de los idiomas de trabajo de [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore). La defaultLabel debe ser única para todos los [Términos](/dotnet/api/microsoft.sharepoint.taxonomy.term) del mismo [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), en el mismo nivel jerárquico.

**sharepoint-taxonomy:termSetName**

Obtiene y establece el nombre del objeto TermSet actual.

Esta es la etiqueta léxica de un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), en un lenguaje de trabajo [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Se trata de un parámetro obligatorio para un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Se usa para representar visualmente un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).

La sintaxis para definir un termSetName es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Obtiene y establece el nombre de propiedad del objeto TermSet actual.

Se trata de la etiqueta léxica para una sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm y sharepoint-taxonomy:CustomPropertyForTermSet en un idioma de trabajo de [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).

La taxonomía de sharepoint: propertyName se trata como la clave de CustomProperty.

La sintaxis para definir un propertyName es la siguiente:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Etiquetas opcionales

También puede agregar etiquetas opcionales a la taxonomía.

**sharepoint-taxonomy:otherLabel**

Se trata de la etiqueta léxica alternativa para un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir una otherLabel es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Relaciones semánticas

Las taxonomías tienen una relación jerárquica y, en ocasiones, una simple relación asociativa de "término relacionado", pero algunas taxonomías tienen "relaciones semánticas" o relaciones de creación personalizada.

**sharepoint-taxonomy:parent**

This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir un término principal es la siguiente:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Esto significa que el TermA es el principal y el TermA es el secundario.

**sharepoint-taxonomy:child**

El objeto contiene una o más instancias de TermSet secundarias, y se puede acceder a ellas mediante la propiedad TermSets. Esta clase también proporciona métodos para crear nuevos objetos TermSet secundarios. Los permisos para editar instancias secundarias de Term y TermSet se especifican en el grupo.

Relaciona de forma jerárquica un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) a otro [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir un término secundario es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Esto significa que el TermA es el principal y el TermA es el secundario.

## <a name="documentation-notes"></a>Notas de documentación

En esta sección se explica la taxonomía detallada en el espacio de nombres Microsoft.SharePoint.Taxonomy.

**sharepoint-taxonomy:description**

Se trata de una explicación detallada de cualquier entidad de vocabulario de la [taxonomía de SharePoint](/dotnet/api/microsoft.sharepoint.taxonomy).

La sintaxis para agregar una descripción es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Propiedades personalizadas

Obtiene la colección de objetos de la propiedad personalizada del objeto término actual del diccionario de solo lectura.

Las propiedades personalizadas son pares de valores clave que se pueden definir para un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), con el fin de ampliar la descripción del [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) o de un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint especifica la clave de la propiedad personalizada con la ayuda de propertyName.

**sharepoint-taxonomy:CustomPropertyForTermSet**

La sintaxis para definirlo es la siguiente:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

Si es necesario llevar la propiedad personalizada para un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) junto con el [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en SharedCustomPropertyForTerm.

La sintaxis para definirlo es la siguiente:

```SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

Si no es necesario llevar la propiedad personalizada de un [término](/dotnet/api/microsoft.sharepoint.taxonomy.term) junto con el [término](/dotnet/api/microsoft.sharepoint.taxonomy.term), al reutilizar el [término](/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en LocalCustomPropertyForTerm.

La sintaxis para definirlo es la siguiente:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Propiedades de datos

En cada nivel de la jerarquía, puede configurar las propiedades específicas de datos para un término o TermSet.

**sharepoint-taxonomy:isAvailableForTagging**

Úsela para especificar si un [Término](/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponible en las listas y bibliotecas de SharePoint.

La sintaxis de esto es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Dominio y rango

En la tabla siguiente se describen el dominio y el rango del vocabulario de la taxonomía de SharePoint.

|Predicados/verbo|Significado|Dominio|Range|
|:--------------|:------|:-----|:----|
inTermSet|En conjunto de términos|Término|Conjunto de términos|
inTermGroup|En grupo de términos|TermSet|TermGroup|
topLevelTermOf|Es el término de nivel superior de|Término|TermSet|
hasTopLevelTerm|Tiene el término de nivel superior|Conjunto de términos|Término|
termSetName|El conjunto de términos tiene el nombre|Término|Literal simple|
defaultLabel|El término tiene una etiqueta predeterminada|Término|Literal simple|
otherLabel|El término tiene otra etiqueta|Término|Literal simple|
propertyName|Tiene etiqueta de propiedad|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Booleano, cadena, entero, decimal, doble|
|description|Tiene descripción|Todo|Literal simple|
|primario|Tiene primario|Término|Término|
|secundario|Tiene secundario|Término|Término|
|isAvailableForTagging|Está disponible para etiquetado|Término, conjunto de términos|Booleano|
|SharedCustomPropertyForTerm|Tiene propiedad personalizada compartida|Término|Booleano, cadena, entero, decimal, doble|
|LocalCustomPropertyForTerm|Tiene propiedad personalizada local|Término|Booleano, cadena, entero, decimal, doble|
|CustomPropertyForTermSet|Tiene propiedad personalizada|TermSet|Booleano, cadena, entero, decimal, doble|

Escenarios válidos de [SKOS](https://www.w3.org/TR/skos-primer/) que la [taxonomía de SharePoint](/dotnet/api/microsoft.sharepoint.taxonomy) no permite:

- Redundancia jerárquica: un concepto [de SKOS](https://www.w3.org/TR/skos-primer/) se puede asociar a varios conceptos más amplios al mismo tiempo, pero una taxonomía de sharepoint:Term solo puede tener un sharepoint-taxonomy:parent, por lo tanto, no se permite la dependencia cíclica de los Términos.
- Los términos huérfanos no se permiten en la taxonomía de SharePoint. Cada taxonomía de sharepoint: el término debe tener una taxonomía de sharepoint: parent o debe ser la taxonomía de sharepoint: topLevelTermOf a TermSet.
- La taxonomía de SharePoint no admite relaciones asociativas.
- La taxonomía de SharePoint solo permite dos tipos de relaciones jerárquicas: sharepoint-taxonomy: parent y sharepoint-Taxonomy: child.
- A diferencia de [SKOS](https://www.w3.org/TR/skos-primer/), la relación jerárquica en el vocabulario de la taxonomía de SharePoint solo se puede establecer con términos del mismo TermSet.

## <a name="see-also"></a>Consulte también

[Importar un conjunto de términos con un formato basado en SKOS](import-term-set-skos.md)
