---
title: Referencia de formato SKOS para la taxonomía de SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: Referencia de formato SKOS para la taxonomía de SharePoint
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296085"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Referencia de formato SKOS para la taxonomía de SharePoint

Este artículo incluye el vocabulario de RDF que se usa para representar la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) y se basa en [SKOS](https://www.w3.org/TR/skos-primer/). Para serialización de esta sintaxis RDF, use RDF [tortuga](https://www.w3.org/TR/turtle/).

En la siguiente tabla se muestran los equivalentes de [SKOS](https://www.w3.org/TR/skos-primer/) para el vocabulario de la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . SharePoint no admite valores de [SKOS](https://www.w3.org/TR/skos-primer/) que no tengan un equivalente de taxonomía de SharePoint.

|Taxonomía de SharePoint|Equivalente de SKOS|
|:-----------------|:--------------|
|SharePoint-taxonomía: Term|SKOS: concepto|
|SharePoint-taxonomía: TermSet|skos:ConceptScheme|
|SharePoint-taxonomía: inTermSet|SKOS: inscheme|
|SharePoint-taxonomía: hasTopLevelTerm|skos:hasTopConcept|
|SharePoint-taxonomía: topLevelTermOf|SKOS: el principio|
|SharePoint-taxonomía: defaultLabel|skos:prefLabel|
|SharePoint-taxonomía: termSetName|skos:prefLabel|
|SharePoint-taxonomía: propertyName|skos:prefLabel|
|SharePoint-taxonomía: otherLabel|skos:altLabel|
|SharePoint-taxonomía: Descripción|SKOS: definición|
|SharePoint-taxonomía: principal|SKOS: más amplio|
|SharePoint-taxonomía: secundaria|SKOS: más estrecho|

En la siguiente tabla se muestran las entidades del vocabulario de la taxonomía de SharePoint derivadas de [OWL](https://www.w3.org/TR/owl2-primer/).

|Vocabulario de taxonomía de SharePoint|Derivadas de OWL|
|:-----------------------------|:----------------------|
|SharePoint-taxonomía: isAvailableForTagging|owl:datatypeproperty|
|SharePoint-taxonomía: SharedCustomPropertyForTerm|OWL: ObjectProperty|
|SharePoint-taxonomía: LocalCustomPropertyForTerm|OWL: ObjectProperty|
|SharePoint-taxonomía: CustomPropertyForTermSet|OWL: ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabulario de taxonomía de SharePoint

Una taxonomía es un sistema de clasificación formal. Una taxonomía agrupa las palabras, los rótulos y los términos que describen algo y, a continuación, organiza los grupos en una jerarquía.

**SharePoint-taxonomía: Term**

Representa un término o una palabra clave en una jerarquía de metadatos administrados.

Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la unidad atómica de un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)de SharePoint. Cada [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenece a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertenece a un [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

La sintaxis para definir un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la siguiente:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Existe un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) obligatorio dentro de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel es el nombre del [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tal como aparece en la representación visual. Los campos obligatorios para definir un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluyen:

- SharePoint-taxonomía: defaultLabel
- SharePoint-taxonomía: inTermSet

Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede:

- Estar relacionada jerárquicamente con otro [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que se proporciona ambos [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenecen al mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tener varios [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)secundarios, pero solo un único [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario.
- No tener un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) primario definido, si es un topLevelTermOf de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tener un defaultLabel, por idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .
- No existir si no contiene un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario, o no es el topLevelTermOf de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Tener un defaultLabel único en el mismo nivel jerárquico.

**SharePoint-taxonomía: TermSet**

Representa un conjunto jerárquico o plano de objetos Term denominado “TermSet”.

Como sugiere el nombre, TermSet es un conjunto de [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) debe pertenecer a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Ningún [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede existir de forma independiente. 

La sintaxis para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es la siguiente:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) se agrupan de forma lógica juntos en [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). El campo obligatorio para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es el siguiente:

- SharePoint-taxonomía: termSetName

En el caso del termSetName proporcionado no es único dentro del [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint agrega un número al final del nombre para mantener la exclusividad de termSetName (s).

**SharePoint-taxonomía: hasTopLevelTerm**

SharePoint usa esta propiedad para asignar el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) más alto en el [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que es el punto de entrada a la jerarquía de [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Esta es una relación inversa con la taxonomía de SharePoint: topLevelTermOf. 

La sintaxis para definir esto es:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> No se puede definir el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario.

**SharePoint-taxonomía: topLevelTermOf**

SharePoint-taxonomía: topLevelTermOf es el inverso de la taxonomía de SharePoint: hasTopLevelTerm

La sintaxis para definir esto es:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**SharePoint-taxonomía: inTermSet**

Use esta para asignar un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) solo puede existir en un solo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint requiere esta propiedad al [definir un término](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Etiquetas necesarias

Es posible que su organización desee realizar un plan minucioso antes de empezar a usar metadatos administrados. La cantidad de planeación que debe realizar depende de cómo forma la taxonomía. También depende de la cantidad de control que desee imponer sobre los metadatos. En cada nivel de la jerarquía, debe configurar etiquetas requeridas para term o TermSet.

Un término puede tener una o más etiquetas en el idioma predeterminado y cero o más etiquetas en el idioma no predeterminado. Si el término tiene etiquetas en un idioma, una de las etiquetas debe ser la etiqueta predeterminada.

**SharePoint-taxonomía: defaultLabel**

Use esta etiqueta léxica predeterminada para un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que es un parámetro obligatorio para un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Se usa para representar visualmente el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir un defaultLabel es:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel contiene dos partes: la cadena y la etiqueta de idioma. El idioma debe ser uno de los idiomas de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . El defaultLabel debe ser único para todos los [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en el mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en el mismo nivel jerárquico.

**SharePoint-taxonomía: termSetName**

Obtiene y establece el nombre del objeto TermSet actual.

Esta es la etiqueta léxica de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Se trata de un parámetro obligatorio para [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Se usa para representar visualmente un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

La sintaxis para definir un termSetName es:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**SharePoint-taxonomía: propertyName**

Obtiene y establece el nombre de propiedad para el objeto TermSet actual.

Esta es la etiqueta léxica de una taxonomía de SharePoint: SharedCustomPropertyForTerm, SharePoint-Taxonomy: LocalCustomPropertyForTerm y SharePoint-Taxonomy: CustomPropertyForTermSet en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .

SharePoint-Taxonomy: propertyName se trata como la clave de la CustomProperty.

La sintaxis para definir un propetyName es:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Etiquetas opcionales

También puede agregar etiquetas opcionales a su taxonomía.

**SharePoint-taxonomía: otherLabel**

Esta es la etiqueta léxica alternativa de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

La sintaxis para definir un otherLabel es:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Relaciones semánticas

Las taxonomías tienen una relación asociativa jerárquica y a veces "" término relacionado ", pero algunas tienen" relaciones semánticas "o relaciones creadas de forma personalizada. 

**SharePoint-taxonomía: principal**

Esta jerarquía relaciona jerárquicamente un [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) con otro [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede ser un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), pero en caso de que no debe tener un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario. 

La sintaxis para definir un elemento primario es:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Esto significa que TermA1 tiene el término primario. Por el contrario, también significa que TermA1 es el elemento secundario de terma. La relación de elementos principales y secundarios es una relación inverso.

**SharePoint-taxonomía: secundaria**

El objeto contiene una o varias instancias TermSet secundarias, y se puede tener acceso a ellas a través de la propiedad TermSets. Esta clase también proporciona métodos para crear nuevos objetos TermSet secundarios. Los permisos para editar las instancias de term secundario y TermSet se especifican en el grupo. 

Esta jerarquía relaciona jerárquicamente un [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) con otro [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintaxis para definir un elemento secundario es:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Esto significa que terma tiene TermA1 secundarios. Por el contrario, también significa que la relación primaria-secundaria de TermA1 es la relación inverso.

## <a name="documentation-notes"></a>Notas de la documentación

En esta sección se describe la taxonomía detallada en el espacio de nombres Microsoft. SharePoint. Taxonomy.

**SharePoint-taxonomía: Descripción**

Esta es una explicación detallada de cualquier entidad de vocabulario de [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . 

La sintaxis para agregar una descripción es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Propiedades personalizadas

Obtiene la colección de objetos Property personalizados del objeto term actual a partir del Diccionario de solo lectura.

Las propiedades personalizadas son pares de valores clave que se pueden definir para un [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), para seguir la descripción del [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o de un [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint especifica la clave de la propiedad personalizada con la ayuda de propertyName.

**SharePoint-taxonomía: CustomPropertyForTermSet**

La sintaxis para definir esto es:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**SharePoint-taxonomía: SharedCustomPropertyForTerm**

Si la propiedad personalizada de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) debe transferirse junto con el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, debe definirlo en SharedCustomPropertyForTerm.

La sintaxis para definir esto es:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**SharePoint-taxonomía: LocalCustomPropertyForTerm**

Si no es necesario que la propiedad personalizada de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) se lleve a cabo junto con el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en LocalCustomPropertyForTerm.

La sintaxis para definir esto es:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Propiedades de datos

En cada nivel de la jerarquía, puede configurar propiedades de datos específicas para un term o TermSet.

**SharePoint-taxonomía: isAvailableForTagging**

Use esta para especificar si un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponible en listas y bibliotecas de SharePoint.  

La sintaxis es la siguiente:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Dominio y intervalo

En la tabla siguiente se describe el dominio y el rango de vocabulario de la taxonomía de SharePoint.

|Predicados/verbo|Significado|Dominio|Range|
|:--------------|:------|:-----|:----|
inTermSet|En el conjunto de términos|Term|Conjunto de términos|
inTermGroup|En el grupo de términos|TermSet|TermGroup|
topLevelTermOf|Es el período de nivel superior de|Term|TermSet|
hasTopLevelTerm|Tiene un término de nivel superior|Conjunto de términos|Term|
termSetName|El conjunto de términos tiene el nombre|Term|Literal sin formato|
defaultLabel|El término tiene una etiqueta predeterminada|Term|Literal sin formato|
otherLabel|El término tiene otra etiqueta|Term|Literal sin formato|
propertyName|Tiene etiqueta de propiedad|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, integer, decimal, Double|
|description|Tiene una descripción|Todo|Literal sin formato|
|primario|Tiene un elemento primario|Term|Term|
|hija|Tiene un elemento secundario|Term|Term|
|isAvailableForTagging|Está disponible para etiquetado|Término, conjunto de términos|Boolean|
|SharedCustomPropertyForTerm|Tiene la propiedad personalizada Shared|Term|Boolean, String, integer, decimal, Double|
|LocalCustomPropertyForTerm|Tiene propiedad personalizada local|Term|Boolean, String, integer, decimal, Double|
|CustomPropertyForTermSet|Tiene una propiedad personalizada|TermSet|Boolean, String, integer, decimal, Double|

[SKOS](https://www.w3.org/TR/skos-primer/) escenarios válidos que la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) no permite:

- Redundancia jerárquica: un concepto de [SKOS](https://www.w3.org/TR/skos-primer/) se puede adjuntar a varios conceptos más amplios al mismo tiempo, pero una taxonomía de SharePoint: Term solo puede tener una taxonomía de SharePoint: el elemento primario, por lo tanto, la dependencia cíclica, de los términos tampoco se permite.
- Los términos huérfanos no se permiten en la taxonomía de SharePoint. Cada taxonomía de SharePoint: Term debe tener una taxonomía de SharePoint: principal o bien la taxonomía de SharePoint: topLevelTermOf un TermSet.
- La taxonomía de SharePoint no admite relaciones asociativas.
- La taxonomía de SharePoint solo permite 2 tipos de relaciones jerárquicas: SharePoint-Taxonomy: principal y SharePoint-taxonomía: secundario. 
- A diferencia de [SKOS](https://www.w3.org/TR/skos-primer/) la relación jerárquica en el vocabulario de la taxonomía de SharePoint, solo se puede establecer con términos dentro del mismo TermSet.

## <a name="see-also"></a>Consulte también

[Importar un conjunto de términos mediante un formato basado en SKOS](import-term-set-skos.md)

