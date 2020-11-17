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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="5c67a-103">Referencia de formato SKOS para la taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="5c67a-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="5c67a-104">Este artículo incluye el vocabulario de RDF usado para representar la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) y se basa en [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="5c67a-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="5c67a-105">Para serializar esta sintaxis RDF, utilice RDF [TURTLE](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="5c67a-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="5c67a-106">En la tabla siguiente se muestran los equivalentes de [SKOS](https://www.w3.org/TR/skos-primer/) para el vocabulario de la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="5c67a-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="5c67a-107">SharePoint no es compatible con aquellos valores de [SKOS](https://www.w3.org/TR/skos-primer/) que no tengan equivalentes de la taxonomía de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c67a-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="5c67a-108">Taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="5c67a-108">SharePoint taxonomy</span></span>|<span data-ttu-id="5c67a-109">Equivalente de SKOS</span><span class="sxs-lookup"><span data-stu-id="5c67a-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="5c67a-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="5c67a-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="5c67a-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="5c67a-111">skos:Concept</span></span>|
|<span data-ttu-id="5c67a-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="5c67a-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="5c67a-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="5c67a-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="5c67a-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="5c67a-115">skos:inScheme</span></span>|
|<span data-ttu-id="5c67a-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="5c67a-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="5c67a-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="5c67a-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="5c67a-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="5c67a-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="5c67a-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="5c67a-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="5c67a-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="5c67a-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-121">skos:prefLabel</span></span>|
|<span data-ttu-id="5c67a-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="5c67a-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="5c67a-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-123">skos:prefLabel</span></span>|
|<span data-ttu-id="5c67a-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="5c67a-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="5c67a-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-125">skos:prefLabel</span></span>|
|<span data-ttu-id="5c67a-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="5c67a-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-127">skos:altLabel</span></span>|
|<span data-ttu-id="5c67a-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="5c67a-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="5c67a-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="5c67a-129">skos:definition</span></span>|
|<span data-ttu-id="5c67a-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="5c67a-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="5c67a-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="5c67a-131">skos:broader</span></span>|
|<span data-ttu-id="5c67a-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="5c67a-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="5c67a-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="5c67a-133">skos:narrower</span></span>|

<span data-ttu-id="5c67a-134">En la tabla siguiente se muestran las entidades del vocabulario de la taxonomía de SharePoint derivados de [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="5c67a-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="5c67a-135">Vocabulario de la taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="5c67a-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="5c67a-136">Derivado de OWL</span><span class="sxs-lookup"><span data-stu-id="5c67a-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="5c67a-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="5c67a-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="5c67a-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="5c67a-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="5c67a-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="5c67a-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="5c67a-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="5c67a-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="5c67a-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="5c67a-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="5c67a-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="5c67a-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="5c67a-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="5c67a-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="5c67a-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="5c67a-145">Vocabulario de la taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="5c67a-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="5c67a-146">Una taxonomía es un sistema de clasificación formal.</span><span class="sxs-lookup"><span data-stu-id="5c67a-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="5c67a-147">Una taxonomía agrupa las palabras, las etiquetas y los términos que describen algo y, a continuación, organiza los grupos en una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="5c67a-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="5c67a-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="5c67a-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="5c67a-149">Representa un término o una palabra clave en una jerarquía de metadatos administrados.</span><span class="sxs-lookup"><span data-stu-id="5c67a-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="5c67a-150">Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la unidad atómica de un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c67a-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="5c67a-151">Cada [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenece a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertenece a un [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="5c67a-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="5c67a-152">La sintaxis para definir un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="5c67a-153">Obligatoriamente, existe un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="5c67a-154">DefaultLabel es el nombre del [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tal y como aparece en la representación visual.</span><span class="sxs-lookup"><span data-stu-id="5c67a-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="5c67a-155">Los campos obligatorios para definir un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluyen:</span><span class="sxs-lookup"><span data-stu-id="5c67a-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="5c67a-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="5c67a-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="5c67a-158">Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede:</span><span class="sxs-lookup"><span data-stu-id="5c67a-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="5c67a-159">Estar relacionado jerárquicamente con otro [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), siempre y cuando ambos [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenezcan al mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="5c67a-160">Tener varios [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) secundarios, pero un único [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal.</span><span class="sxs-lookup"><span data-stu-id="5c67a-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="5c67a-161">No tener un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) definido, si se trata de un término de nivel superior (topLevelTermOf) de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="5c67a-162">Tener una única defaultLabel por idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="5c67a-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="5c67a-163">No existir en caso de que no contenga un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal y de que no sea el término de nivel superior (topLevelTermOf) de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="5c67a-164">Tener una única defaultLabel en el mismo nivel jerárquico.</span><span class="sxs-lookup"><span data-stu-id="5c67a-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="5c67a-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="5c67a-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="5c67a-166">Representa un conjunto jerárquico o plano de objetos Term denominado "TermSet".</span><span class="sxs-lookup"><span data-stu-id="5c67a-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="5c67a-167">Como el nombre sugiere, TermSet es un conjunto de [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="5c67a-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="5c67a-168">Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) debe pertenecer a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="5c67a-169">Ningún [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede existir de manera independiente.</span><span class="sxs-lookup"><span data-stu-id="5c67a-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="5c67a-170">La sintaxis para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="5c67a-171">Los [TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) se agrupan lógicamente en [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="5c67a-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="5c67a-172">El campo obligatorio para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="5c67a-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="5c67a-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="5c67a-174">En aquellos casos en los que el termSetName proporcionado no sea único en el [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint anexará un número al final del nombre para mantener la exclusividad del termSetName.</span><span class="sxs-lookup"><span data-stu-id="5c67a-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="5c67a-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="5c67a-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="5c67a-176">SharePoint usa esta propiedad para asignar el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) superior del [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que constituye el punto de entrada a la jerarquía de los [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="5c67a-177">Se trata de una relación inversa con respecto a sharepoint-taxonomy:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="5c67a-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="5c67a-178">La sintaxis para definirlo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="5c67a-179">No se puede definir el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal.</span><span class="sxs-lookup"><span data-stu-id="5c67a-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="5c67a-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="5c67a-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="5c67a-181">Sharepoint-taxonomy:topLevelTermOf constituye el contrario de sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="5c67a-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="5c67a-182">La sintaxis para definirlo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="5c67a-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="5c67a-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="5c67a-184">Use esto para asignar un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="5c67a-185">Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) solo puede existir en un único [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="5c67a-186">SharePoint requiere esta propiedad a la hora de [definir un término](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="5c67a-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="5c67a-187">Etiquetas necesarias</span><span class="sxs-lookup"><span data-stu-id="5c67a-187">Required labels</span></span>

<span data-ttu-id="5c67a-188">Antes de que usted empiece a usar metadatos administrados, resulta conveniente que su organización planifique cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="5c67a-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="5c67a-189">La cantidad de planificación que debe llevar a cabo dependerá del grado de formalidad de su taxonomía.</span><span class="sxs-lookup"><span data-stu-id="5c67a-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="5c67a-190">Asimismo, dependerá de la cantidad de control que desee aplicar a los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5c67a-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="5c67a-191">En cada nivel de la jerarquía, tiene que configurar las etiquetas obligatorias para un término o TermSet.</span><span class="sxs-lookup"><span data-stu-id="5c67a-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="5c67a-192">Un término puede tener una o más etiquetas en el idioma predeterminado, y ninguna, una o varias etiquetas en el idioma no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5c67a-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="5c67a-193">Si el término tiene etiquetas en un idioma, una de ellas debe ser la etiqueta predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c67a-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="5c67a-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="5c67a-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="5c67a-195">Use esta etiqueta léxica predeterminada para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term); se trata de un parámetro necesario para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="5c67a-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="5c67a-196">Se usa para representar visualmente el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="5c67a-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="5c67a-197">La sintaxis para definir una defaultLabel (etiqueta predeterminada) es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="5c67a-198">La DefaultLabel contiene dos partes: la cadena y la etiqueta de idioma.</span><span class="sxs-lookup"><span data-stu-id="5c67a-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="5c67a-199">El idioma debe ser uno de los idiomas de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="5c67a-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="5c67a-200">La defaultLabel debe ser única para todos los [Términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) del mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en el mismo nivel jerárquico.</span><span class="sxs-lookup"><span data-stu-id="5c67a-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="5c67a-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="5c67a-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="5c67a-202">Obtiene y establece el nombre del objeto TermSet actual.</span><span class="sxs-lookup"><span data-stu-id="5c67a-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="5c67a-203">Esta es la etiqueta léxica de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="5c67a-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="5c67a-204">Se trata de un parámetro obligatorio para un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="5c67a-205">Se usa para representar visualmente un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="5c67a-206">La sintaxis para definir un termSetName es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="5c67a-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="5c67a-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="5c67a-208">Obtiene y establece el nombre de propiedad del objeto TermSet actual.</span><span class="sxs-lookup"><span data-stu-id="5c67a-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="5c67a-209">Se trata de la etiqueta léxica para una sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm y sharepoint-taxonomy:CustomPropertyForTermSet en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="5c67a-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="5c67a-210">La sharepoint-taxonomy:propertyName se trata como la clave de la CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="5c67a-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="5c67a-211">La sintaxis para definir un propertyName es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="5c67a-212">Etiquetas opcionales</span><span class="sxs-lookup"><span data-stu-id="5c67a-212">Optional labels</span></span>

<span data-ttu-id="5c67a-213">También puede agregar etiquetas opcionales a la taxonomía.</span><span class="sxs-lookup"><span data-stu-id="5c67a-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="5c67a-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="5c67a-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="5c67a-215">Se trata de la etiqueta léxica alternativa para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="5c67a-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="5c67a-216">La sintaxis para definir una otherLabel es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="5c67a-217">Relaciones semánticas</span><span class="sxs-lookup"><span data-stu-id="5c67a-217">Semantic relationships</span></span>

<span data-ttu-id="5c67a-218">Las taxonomías tienen una relación jerárquica y, en ocasiones, una simple relación asociativa de "término relacionado", pero algunas taxonomías tienen "relaciones semánticas" o relaciones de creación personalizada.</span><span class="sxs-lookup"><span data-stu-id="5c67a-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="5c67a-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="5c67a-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="5c67a-220">Relaciona de forma jerárquica un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a otro [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="5c67a-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="5c67a-221">Un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) podría ser un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). En caso de no serlo, debe tener un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) principal.</span><span class="sxs-lookup"><span data-stu-id="5c67a-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="5c67a-222">La sintaxis para definir un término principal es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="5c67a-223">Esto significa que el TermA es el principal y el TermA es el secundario.</span><span class="sxs-lookup"><span data-stu-id="5c67a-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="5c67a-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="5c67a-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="5c67a-225">El objeto contiene una o más instancias de TermSet secundarias, y se puede acceder a ellas mediante la propiedad TermSets.</span><span class="sxs-lookup"><span data-stu-id="5c67a-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="5c67a-226">Esta clase también proporciona métodos para crear nuevos objetos TermSet secundarios.</span><span class="sxs-lookup"><span data-stu-id="5c67a-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="5c67a-227">Los permisos para editar las instancias de término y de TermSet secundarios se especifican en el grupo.</span><span class="sxs-lookup"><span data-stu-id="5c67a-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="5c67a-228">Relaciona de forma jerárquica un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a otro [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="5c67a-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="5c67a-229">La sintaxis para definir un término secundario es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="5c67a-230">Esto significa que el TermA es el principal y el TermA es el secundario.</span><span class="sxs-lookup"><span data-stu-id="5c67a-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="5c67a-231">Notas de documentación</span><span class="sxs-lookup"><span data-stu-id="5c67a-231">Documentation notes</span></span>

<span data-ttu-id="5c67a-232">En esta sección se explica la taxonomía detallada en el espacio de nombres Microsoft.SharePoint.Taxonomy.</span><span class="sxs-lookup"><span data-stu-id="5c67a-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="5c67a-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="5c67a-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="5c67a-234">Se trata de una explicación detallada de cualquier entidad de vocabulario de la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="5c67a-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="5c67a-235">La sintaxis para agregar una descripción es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="5c67a-236">Propiedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="5c67a-236">Custom properties</span></span>

<span data-ttu-id="5c67a-237">Obtiene la colección de objetos de la propiedad personalizada del objeto término actual del diccionario de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5c67a-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="5c67a-238">Las propiedades personalizadas son pares de valores clave que se pueden definir para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), con el fin de ampliar la descripción del [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="5c67a-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="5c67a-239">SharePoint especifica la clave de la propiedad personalizada con la ayuda de propertyName.</span><span class="sxs-lookup"><span data-stu-id="5c67a-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="5c67a-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="5c67a-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="5c67a-241">La sintaxis para definirlo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="5c67a-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="5c67a-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="5c67a-243">Si es necesario llevar la propiedad personalizada para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) junto con el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="5c67a-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="5c67a-244">La sintaxis para definirlo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="5c67a-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="5c67a-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="5c67a-246">Si no resulta necesario llevar la propiedad personalizada para un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) junto con el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="5c67a-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="5c67a-247">La sintaxis para definirlo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="5c67a-248">Propiedades de datos</span><span class="sxs-lookup"><span data-stu-id="5c67a-248">Data properties</span></span>

<span data-ttu-id="5c67a-249">En cada nivel de la jerarquía, puede configurar las propiedades específicas de datos para un término o TermSet.</span><span class="sxs-lookup"><span data-stu-id="5c67a-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="5c67a-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="5c67a-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="5c67a-251">Úsela para especificar si un [Término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponible en las listas y bibliotecas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c67a-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="5c67a-252">La sintaxis de esto es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c67a-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="5c67a-253">Dominio y rango</span><span class="sxs-lookup"><span data-stu-id="5c67a-253">Domain and range</span></span>

<span data-ttu-id="5c67a-254">En la tabla siguiente se describen el dominio y el rango del vocabulario de la taxonomía de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c67a-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="5c67a-255">Predicados/verbo</span><span class="sxs-lookup"><span data-stu-id="5c67a-255">Predicates/verb</span></span>|<span data-ttu-id="5c67a-256">Significado</span><span class="sxs-lookup"><span data-stu-id="5c67a-256">Meaning</span></span>|<span data-ttu-id="5c67a-257">Dominio</span><span class="sxs-lookup"><span data-stu-id="5c67a-257">Domain</span></span>|<span data-ttu-id="5c67a-258">Range</span><span class="sxs-lookup"><span data-stu-id="5c67a-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="5c67a-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-259">inTermSet</span></span>|<span data-ttu-id="5c67a-260">En conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="5c67a-260">In term set</span></span>|<span data-ttu-id="5c67a-261">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-261">Term</span></span>|<span data-ttu-id="5c67a-262">Conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="5c67a-262">Term Set</span></span>|
<span data-ttu-id="5c67a-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="5c67a-263">inTermGroup</span></span>|<span data-ttu-id="5c67a-264">En grupo de términos</span><span class="sxs-lookup"><span data-stu-id="5c67a-264">In term group</span></span>|<span data-ttu-id="5c67a-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-265">TermSet</span></span>|<span data-ttu-id="5c67a-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="5c67a-266">TermGroup</span></span>|
<span data-ttu-id="5c67a-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="5c67a-267">topLevelTermOf</span></span>|<span data-ttu-id="5c67a-268">Es el término de nivel superior de</span><span class="sxs-lookup"><span data-stu-id="5c67a-268">Is Top Level Term Of</span></span>|<span data-ttu-id="5c67a-269">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-269">Term</span></span>|<span data-ttu-id="5c67a-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-270">TermSet</span></span>|
<span data-ttu-id="5c67a-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="5c67a-271">hasTopLevelTerm</span></span>|<span data-ttu-id="5c67a-272">Tiene el término de nivel superior</span><span class="sxs-lookup"><span data-stu-id="5c67a-272">Has top level term</span></span>|<span data-ttu-id="5c67a-273">Conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="5c67a-273">Term Set</span></span>|<span data-ttu-id="5c67a-274">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-274">Term</span></span>|
<span data-ttu-id="5c67a-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="5c67a-275">termSetName</span></span>|<span data-ttu-id="5c67a-276">El conjunto de términos tiene el nombre</span><span class="sxs-lookup"><span data-stu-id="5c67a-276">Term set has Name</span></span>|<span data-ttu-id="5c67a-277">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-277">Term</span></span>|<span data-ttu-id="5c67a-278">Literal simple</span><span class="sxs-lookup"><span data-stu-id="5c67a-278">Plain literal</span></span>|
<span data-ttu-id="5c67a-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-279">defaultLabel</span></span>|<span data-ttu-id="5c67a-280">El término tiene una etiqueta predeterminada</span><span class="sxs-lookup"><span data-stu-id="5c67a-280">Term has default label</span></span>|<span data-ttu-id="5c67a-281">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-281">Term</span></span>|<span data-ttu-id="5c67a-282">Literal simple</span><span class="sxs-lookup"><span data-stu-id="5c67a-282">Plain literal</span></span>|
<span data-ttu-id="5c67a-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="5c67a-283">otherLabel</span></span>|<span data-ttu-id="5c67a-284">El término tiene otra etiqueta</span><span class="sxs-lookup"><span data-stu-id="5c67a-284">Term has other label</span></span>|<span data-ttu-id="5c67a-285">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-285">Term</span></span>|<span data-ttu-id="5c67a-286">Literal simple</span><span class="sxs-lookup"><span data-stu-id="5c67a-286">Plain literal</span></span>|
<span data-ttu-id="5c67a-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="5c67a-287">propertyName</span></span>|<span data-ttu-id="5c67a-288">Tiene etiqueta de propiedad</span><span class="sxs-lookup"><span data-stu-id="5c67a-288">Has Property Label</span></span>|<span data-ttu-id="5c67a-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="5c67a-290">Booleano, cadena, entero, decimal, doble</span><span class="sxs-lookup"><span data-stu-id="5c67a-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="5c67a-291">description</span><span class="sxs-lookup"><span data-stu-id="5c67a-291">description</span></span>|<span data-ttu-id="5c67a-292">Tiene descripción</span><span class="sxs-lookup"><span data-stu-id="5c67a-292">Has Description</span></span>|<span data-ttu-id="5c67a-293">Todo</span><span class="sxs-lookup"><span data-stu-id="5c67a-293">All</span></span>|<span data-ttu-id="5c67a-294">Literal simple</span><span class="sxs-lookup"><span data-stu-id="5c67a-294">Plain literal</span></span>|
|<span data-ttu-id="5c67a-295">primario</span><span class="sxs-lookup"><span data-stu-id="5c67a-295">parent</span></span>|<span data-ttu-id="5c67a-296">Tiene primario</span><span class="sxs-lookup"><span data-stu-id="5c67a-296">Has parent</span></span>|<span data-ttu-id="5c67a-297">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-297">Term</span></span>|<span data-ttu-id="5c67a-298">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-298">Term</span></span>|
|<span data-ttu-id="5c67a-299">secundario</span><span class="sxs-lookup"><span data-stu-id="5c67a-299">child</span></span>|<span data-ttu-id="5c67a-300">Tiene secundario</span><span class="sxs-lookup"><span data-stu-id="5c67a-300">Has Child</span></span>|<span data-ttu-id="5c67a-301">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-301">Term</span></span>|<span data-ttu-id="5c67a-302">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-302">Term</span></span>|
|<span data-ttu-id="5c67a-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="5c67a-303">isAvailableForTagging</span></span>|<span data-ttu-id="5c67a-304">Está disponible para etiquetado</span><span class="sxs-lookup"><span data-stu-id="5c67a-304">Is available for tagging</span></span>|<span data-ttu-id="5c67a-305">Término, conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="5c67a-305">Term, Term Set</span></span>|<span data-ttu-id="5c67a-306">Booleano</span><span class="sxs-lookup"><span data-stu-id="5c67a-306">Boolean</span></span>|
|<span data-ttu-id="5c67a-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="5c67a-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="5c67a-308">Tiene propiedad personalizada compartida</span><span class="sxs-lookup"><span data-stu-id="5c67a-308">Has shared custom property</span></span>|<span data-ttu-id="5c67a-309">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-309">Term</span></span>|<span data-ttu-id="5c67a-310">Booleano, cadena, entero, decimal, doble</span><span class="sxs-lookup"><span data-stu-id="5c67a-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="5c67a-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="5c67a-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="5c67a-312">Tiene propiedad personalizada local</span><span class="sxs-lookup"><span data-stu-id="5c67a-312">Has local custom property</span></span>|<span data-ttu-id="5c67a-313">Término</span><span class="sxs-lookup"><span data-stu-id="5c67a-313">Term</span></span>|<span data-ttu-id="5c67a-314">Booleano, cadena, entero, decimal, doble</span><span class="sxs-lookup"><span data-stu-id="5c67a-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="5c67a-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="5c67a-316">Tiene propiedad personalizada</span><span class="sxs-lookup"><span data-stu-id="5c67a-316">Has Custom Property</span></span>|<span data-ttu-id="5c67a-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="5c67a-317">TermSet</span></span>|<span data-ttu-id="5c67a-318">Booleano, cadena, entero, decimal, doble</span><span class="sxs-lookup"><span data-stu-id="5c67a-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="5c67a-319">Escenarios válidos de [SKOS](https://www.w3.org/TR/skos-primer/) que la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) no permite:</span><span class="sxs-lookup"><span data-stu-id="5c67a-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="5c67a-320">Redundancia jerárquica: un concepto de [SKOS](https://www.w3.org/TR/skos-primer/) se puede adjuntar a varios conceptos más amplios al mismo tiempo, pero una sharepoint-taxonomy:Term solo puede tener una sharepoint-taxonomy:parent, por lo que tampoco se permite la dependencia cíclica de los términos.</span><span class="sxs-lookup"><span data-stu-id="5c67a-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="5c67a-321">No se permiten términos huérfanos en la taxonomía de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c67a-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="5c67a-322">Toda sharepoint-taxonomy:Term debe tener una sharepoint-taxonomy:parent, o bien debe ser la sharepoint-taxonomy:topLevelTermOf de un TermSet.</span><span class="sxs-lookup"><span data-stu-id="5c67a-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="5c67a-323">La taxonomía de SharePoint no admite relaciones asociativas.</span><span class="sxs-lookup"><span data-stu-id="5c67a-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="5c67a-324">La taxonomía de SharePoint solo permite 2 tipos de relación jerárquica: sharepoint-taxonomy:parent y sharepoint-Taxonomy:child.</span><span class="sxs-lookup"><span data-stu-id="5c67a-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="5c67a-325">A diferencia de [SKOS](https://www.w3.org/TR/skos-primer/), la relación jerárquica en el vocabulario de la taxonomía de SharePoint solo se puede establecer con términos del mismo TermSet.</span><span class="sxs-lookup"><span data-stu-id="5c67a-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c67a-326">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c67a-326">See also</span></span>

[<span data-ttu-id="5c67a-327">Importar un conjunto de términos con un formato basado en SKOS</span><span class="sxs-lookup"><span data-stu-id="5c67a-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

