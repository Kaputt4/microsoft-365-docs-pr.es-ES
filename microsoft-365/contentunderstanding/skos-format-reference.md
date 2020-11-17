---
title: Referencia de formato SKOS para la taxonomía de SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Referencia de formato SKOS para la taxonomía de SharePoint
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087289"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Referencia de formato SKOS para la taxonomía de SharePoint

Este artículo incluye el vocabulario de RDF usado para representar la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) y se basa en [SKOS](https://www.w3.org/TR/skos-primer/). Para serializar esta sintaxis RDF, utilice RDF [TURTLE](https://www.w3.org/TR/turtle/).

En la tabla siguiente se muestran los equivalentes de [SKOS](https://www.w3.org/TR/skos-primer/) para el vocabulario de la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). SharePoint no es compatible con aquellos valores de [SKOS](https://www.w3.org/TR/skos-primer/) que no tengan equivalentes de la taxonomía de SharePoint.

|Taxonomía de SharePoint|Equivalente de SKOS|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

En la tabla siguiente se muestran las entidades del vocabulario de la taxonomía de SharePoint derivados de [OWL](https://www.w3.org/TR/owl2-primer/).

|Vocabulario de la taxonomía de SharePoint|Derivado de OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabulario de la taxonomía de SharePoint

Una taxonomía es un sistema de clasificación formal. Una taxonomía agrupa las palabras, las etiquetas y los términos que describen algo y, a continuación, organiza los grupos en una jerarquía.

**sharepoint-taxonomy:Term**

Representa un término o una palabra clave en una jerarquía de metadatos administrados.

Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la unidad atómica de un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) de SharePoint. Cada [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenece a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertenece a un [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

La sintaxis para definir un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la siguiente:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Obligatoriamente, existe un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel es el nombre del [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tal y como aparece en la representación visual. Los campos obligatorios para definir un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluyen:

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede:

- Estar relacionado jerárquicamente con otro [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), siempre y cuando ambos [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenezcan al mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tener varios [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) secundarios, pero un único [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal.
- No tener un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) definido, si se trata de un término de nivel superior (topLevelTermOf) de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tener una única defaultLabel por idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).
- No existir en caso de que no contenga un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal y de que no sea el término de nivel superior (topLevelTermOf) de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Tener una única defaultLabel en el mismo nivel jerárquico.

**sharepoint-taxonomy:TermSet**

Representa un conjunto jerárquico o plano de objetos Term denominado "TermSet".

Como el nombre sugiere, TermSet es un conjunto de [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) debe pertenecer a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Ningún [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede existir de manera independiente. 

La sintaxis para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es la siguiente:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

Los [TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) se agrupan lógicamente en [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). El campo obligatorio para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es el siguiente:

- sharepoint-taxonomy:termSetName

En aquellos casos en los que el termSetName proporcionado no sea único en el [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint anexará un número al final del nombre para mantener la exclusividad del termSetName.

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint usa esta propiedad para asignar el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) superior del [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que constituye el punto de entrada a la jerarquía de los [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Se trata de una relación inversa con respecto a sharepoint-taxonomy:topLevelTermOf. 

La sintaxis para definirlo es la siguiente:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> No se puede definir el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal.

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy:topLevelTermOf constituye el contrario de sharepoint-taxonomy:hasTopLevelTerm

La sintaxis para definirlo es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Use esto para asignar un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) solo puede existir en un único [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint requiere esta propiedad a la hora de [definir un término](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Etiquetas necesarias

Antes de que usted empiece a usar metadatos administrados, resulta conveniente que su organización planifique cuidadosamente. La cantidad de planificación que debe llevar a cabo dependerá del grado de formalidad de su taxonomía. Asimismo, dependerá de la cantidad de control que desee aplicar a los metadatos. En cada nivel de la jerarquía, tiene que configurar las etiquetas obligatorias para un término o TermSet.

Un término puede tener una o más etiquetas en el idioma predeterminado, y ninguna, una o varias etiquetas en el idioma no predeterminado. Si el término tiene etiquetas en un idioma, una de ellas debe ser la etiqueta predeterminada.

**sharepoint-taxonomy:defaultLabel**

Use esta etiqueta léxica predeterminada para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term); se trata de un parámetro necesario para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Se usa para representar visualmente el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir una defaultLabel (etiqueta predeterminada) es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

La DefaultLabel contiene dos partes: la cadena y la etiqueta de idioma. El idioma debe ser uno de los idiomas de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). La defaultLabel debe ser única para todos los [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) del mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en el mismo nivel jerárquico.

**sharepoint-taxonomy:termSetName**

Obtiene y establece el nombre del objeto TermSet actual.

Esta es la etiqueta léxica de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Se trata de un parámetro obligatorio para un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Se usa para representar visualmente un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

La sintaxis para definir un termSetName es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Obtiene y establece el nombre de propiedad del objeto TermSet actual.

Se trata de la etiqueta léxica para una sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm y sharepoint-taxonomy:CustomPropertyForTermSet en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).

La sharepoint-taxonomy:propertyName se trata como la clave de la CustomProperty.

La sintaxis para definir un propertyName es la siguiente:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Etiquetas opcionales

También puede agregar etiquetas opcionales a la taxonomía.

**sharepoint-taxonomy:otherLabel**

Se trata de la etiqueta léxica alternativa para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

La sintaxis para definir una otherLabel es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Relaciones semánticas

Las taxonomías tienen una relación jerárquica y, en ocasiones, una simple relación asociativa de "término relacionado", pero algunas taxonomías tienen "relaciones semánticas" o relaciones de creación personalizada. 

**sharepoint-taxonomy:parent**

Relaciona de forma jerárquica un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a otro [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) podría ser un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). En caso de no serlo, debe tener un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal. 

La sintaxis para definir un término principal es la siguiente:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Esto significa que el TermA es el principal y el TermA es el secundario.

**sharepoint-taxonomy:child**

El objeto contiene una o más instancias de TermSet secundarias, y se puede acceder a ellas mediante la propiedad TermSets. Esta clase también proporciona métodos para crear nuevos objetos TermSet secundarios. Los permisos para editar las instancias de término y de TermSet secundarios se especifican en el grupo. 

Relaciona de forma jerárquica un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a otro [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir un término secundario es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Esto significa que el TermA es el principal y el TermA es el secundario.

## <a name="documentation-notes"></a>Notas de documentación

En esta sección se explica la taxonomía detallada en el espacio de nombres Microsoft.SharePoint.Taxonomy.

**sharepoint-taxonomy:description**

Se trata de una explicación detallada de cualquier entidad de vocabulario de la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). 

La sintaxis para agregar una descripción es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Propiedades personalizadas

Obtiene la colección de objetos de la propiedad personalizada del objeto término actual del diccionario de solo lectura.

Las propiedades personalizadas son pares de valores clave que se pueden definir para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), con el fin de ampliar la descripción del [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint especifica la clave de la propiedad personalizada con la ayuda de propertyName.

**sharepoint-taxonomy:CustomPropertyForTermSet**

La sintaxis para definirlo es la siguiente:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

Si es necesario llevar la propiedad personalizada para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) junto con el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en SharedCustomPropertyForTerm.

La sintaxis para definirlo es la siguiente:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

Si no resulta necesario llevar la propiedad personalizada para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) junto con el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en LocalCustomPropertyForTerm.

La sintaxis para definirlo es la siguiente:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Propiedades de datos

En cada nivel de la jerarquía, puede configurar las propiedades específicas de datos para un término o TermSet.

**sharepoint-taxonomy:isAvailableForTagging**

Úsela para especificar si un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponible en las listas y bibliotecas de SharePoint.  

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

Escenarios válidos de [SKOS](https://www.w3.org/TR/skos-primer/) que la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) no permite:

- Redundancia jerárquica: un concepto de [SKOS](https://www.w3.org/TR/skos-primer/) se puede adjuntar a varios conceptos más amplios al mismo tiempo, pero una sharepoint-taxonomy:Term solo puede tener una sharepoint-taxonomy:parent, por lo que tampoco se permite la dependencia cíclica de los términos.
- No se permiten términos huérfanos en la taxonomía de SharePoint. Toda sharepoint-taxonomy:Term debe tener una sharepoint-taxonomy:parent, o bien debe ser la sharepoint-taxonomy:topLevelTermOf de un TermSet.
- La taxonomía de SharePoint no admite relaciones asociativas.
- La taxonomía de SharePoint solo permite 2 tipos de relación jerárquica: sharepoint-taxonomy:parent y sharepoint-Taxonomy:child. 
- A diferencia de [SKOS](https://www.w3.org/TR/skos-primer/), la relación jerárquica en el vocabulario de la taxonomía de SharePoint solo se puede establecer con términos del mismo TermSet.

## <a name="see-also"></a>Consulte también

[Importar un conjunto de términos con un formato basado en SKOS](import-term-set-skos.md)

