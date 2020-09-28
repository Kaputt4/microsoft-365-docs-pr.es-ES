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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="0692d-103">Referencia de formato SKOS para la taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="0692d-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="0692d-104">Este artículo incluye el vocabulario de RDF que se usa para representar la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) y se basa en [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="0692d-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="0692d-105">Para serialización de esta sintaxis RDF, use RDF [tortuga](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="0692d-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="0692d-106">En la siguiente tabla se muestran los equivalentes de [SKOS](https://www.w3.org/TR/skos-primer/) para el vocabulario de la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="0692d-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="0692d-107">SharePoint no admite valores de [SKOS](https://www.w3.org/TR/skos-primer/) que no tengan un equivalente de taxonomía de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0692d-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="0692d-108">Taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="0692d-108">SharePoint taxonomy</span></span>|<span data-ttu-id="0692d-109">Equivalente de SKOS</span><span class="sxs-lookup"><span data-stu-id="0692d-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="0692d-110">SharePoint-taxonomía: Term</span><span class="sxs-lookup"><span data-stu-id="0692d-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="0692d-111">SKOS: concepto</span><span class="sxs-lookup"><span data-stu-id="0692d-111">skos:Concept</span></span>|
|<span data-ttu-id="0692d-112">SharePoint-taxonomía: TermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="0692d-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="0692d-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="0692d-114">SharePoint-taxonomía: inTermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="0692d-115">SKOS: inscheme</span><span class="sxs-lookup"><span data-stu-id="0692d-115">skos:inScheme</span></span>|
|<span data-ttu-id="0692d-116">SharePoint-taxonomía: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="0692d-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="0692d-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="0692d-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="0692d-118">SharePoint-taxonomía: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="0692d-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="0692d-119">SKOS: el principio</span><span class="sxs-lookup"><span data-stu-id="0692d-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="0692d-120">SharePoint-taxonomía: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="0692d-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-121">skos:prefLabel</span></span>|
|<span data-ttu-id="0692d-122">SharePoint-taxonomía: termSetName</span><span class="sxs-lookup"><span data-stu-id="0692d-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="0692d-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-123">skos:prefLabel</span></span>|
|<span data-ttu-id="0692d-124">SharePoint-taxonomía: propertyName</span><span class="sxs-lookup"><span data-stu-id="0692d-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="0692d-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-125">skos:prefLabel</span></span>|
|<span data-ttu-id="0692d-126">SharePoint-taxonomía: otherLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="0692d-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-127">skos:altLabel</span></span>|
|<span data-ttu-id="0692d-128">SharePoint-taxonomía: Descripción</span><span class="sxs-lookup"><span data-stu-id="0692d-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="0692d-129">SKOS: definición</span><span class="sxs-lookup"><span data-stu-id="0692d-129">skos:definition</span></span>|
|<span data-ttu-id="0692d-130">SharePoint-taxonomía: principal</span><span class="sxs-lookup"><span data-stu-id="0692d-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="0692d-131">SKOS: más amplio</span><span class="sxs-lookup"><span data-stu-id="0692d-131">skos:broader</span></span>|
|<span data-ttu-id="0692d-132">SharePoint-taxonomía: secundaria</span><span class="sxs-lookup"><span data-stu-id="0692d-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="0692d-133">SKOS: más estrecho</span><span class="sxs-lookup"><span data-stu-id="0692d-133">skos:narrower</span></span>|

<span data-ttu-id="0692d-134">En la siguiente tabla se muestran las entidades del vocabulario de la taxonomía de SharePoint derivadas de [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="0692d-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="0692d-135">Vocabulario de taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="0692d-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="0692d-136">Derivadas de OWL</span><span class="sxs-lookup"><span data-stu-id="0692d-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="0692d-137">SharePoint-taxonomía: isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="0692d-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="0692d-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="0692d-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="0692d-139">SharePoint-taxonomía: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0692d-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="0692d-140">OWL: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="0692d-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="0692d-141">SharePoint-taxonomía: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0692d-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="0692d-142">OWL: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="0692d-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="0692d-143">SharePoint-taxonomía: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="0692d-144">OWL: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="0692d-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="0692d-145">Vocabulario de taxonomía de SharePoint</span><span class="sxs-lookup"><span data-stu-id="0692d-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="0692d-146">Una taxonomía es un sistema de clasificación formal.</span><span class="sxs-lookup"><span data-stu-id="0692d-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="0692d-147">Una taxonomía agrupa las palabras, los rótulos y los términos que describen algo y, a continuación, organiza los grupos en una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="0692d-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="0692d-148">**SharePoint-taxonomía: Term**</span><span class="sxs-lookup"><span data-stu-id="0692d-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="0692d-149">Representa un término o una palabra clave en una jerarquía de metadatos administrados.</span><span class="sxs-lookup"><span data-stu-id="0692d-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="0692d-150">Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la unidad atómica de un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0692d-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="0692d-151">Cada [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenece a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertenece a un [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="0692d-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="0692d-152">La sintaxis para definir un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0692d-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="0692d-153">Existe un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) obligatorio dentro de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0692d-154">DefaultLabel es el nombre del [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tal como aparece en la representación visual.</span><span class="sxs-lookup"><span data-stu-id="0692d-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="0692d-155">Los campos obligatorios para definir un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluyen:</span><span class="sxs-lookup"><span data-stu-id="0692d-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="0692d-156">SharePoint-taxonomía: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="0692d-157">SharePoint-taxonomía: inTermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="0692d-158">Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede:</span><span class="sxs-lookup"><span data-stu-id="0692d-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="0692d-159">Estar relacionada jerárquicamente con otro [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que se proporciona ambos [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertenecen al mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="0692d-160">Tener varios [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)secundarios, pero solo un único [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario.</span><span class="sxs-lookup"><span data-stu-id="0692d-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="0692d-161">No tener un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) primario definido, si es un topLevelTermOf de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="0692d-162">Tener un defaultLabel, por idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0692d-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="0692d-163">No existir si no contiene un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario, o no es el topLevelTermOf de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="0692d-164">Tener un defaultLabel único en el mismo nivel jerárquico.</span><span class="sxs-lookup"><span data-stu-id="0692d-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="0692d-165">**SharePoint-taxonomía: TermSet**</span><span class="sxs-lookup"><span data-stu-id="0692d-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="0692d-166">Representa un conjunto jerárquico o plano de objetos Term denominado “TermSet”.</span><span class="sxs-lookup"><span data-stu-id="0692d-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="0692d-167">Como sugiere el nombre, TermSet es un conjunto de [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0692d-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="0692d-168">Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) debe pertenecer a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0692d-169">Ningún [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede existir de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="0692d-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="0692d-170">La sintaxis para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0692d-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="0692d-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) se agrupan de forma lógica juntos en [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="0692d-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="0692d-172">El campo obligatorio para definir un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="0692d-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="0692d-173">SharePoint-taxonomía: termSetName</span><span class="sxs-lookup"><span data-stu-id="0692d-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="0692d-174">En el caso del termSetName proporcionado no es único dentro del [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint agrega un número al final del nombre para mantener la exclusividad de termSetName (s).</span><span class="sxs-lookup"><span data-stu-id="0692d-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="0692d-175">**SharePoint-taxonomía: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="0692d-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="0692d-176">SharePoint usa esta propiedad para asignar el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) más alto en el [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que es el punto de entrada a la jerarquía de [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en un [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0692d-177">Esta es una relación inversa con la taxonomía de SharePoint: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="0692d-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="0692d-178">La sintaxis para definir esto es:</span><span class="sxs-lookup"><span data-stu-id="0692d-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="0692d-179">No se puede definir el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario.</span><span class="sxs-lookup"><span data-stu-id="0692d-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="0692d-180">**SharePoint-taxonomía: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="0692d-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="0692d-181">SharePoint-taxonomía: topLevelTermOf es el inverso de la taxonomía de SharePoint: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="0692d-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="0692d-182">La sintaxis para definir esto es:</span><span class="sxs-lookup"><span data-stu-id="0692d-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="0692d-183">**SharePoint-taxonomía: inTermSet**</span><span class="sxs-lookup"><span data-stu-id="0692d-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="0692d-184">Use esta para asignar un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0692d-185">Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) solo puede existir en un solo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0692d-186">SharePoint requiere esta propiedad al [definir un término](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="0692d-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="0692d-187">Etiquetas necesarias</span><span class="sxs-lookup"><span data-stu-id="0692d-187">Required labels</span></span>

<span data-ttu-id="0692d-188">Es posible que su organización desee realizar un plan minucioso antes de empezar a usar metadatos administrados.</span><span class="sxs-lookup"><span data-stu-id="0692d-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="0692d-189">La cantidad de planeación que debe realizar depende de cómo forma la taxonomía.</span><span class="sxs-lookup"><span data-stu-id="0692d-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="0692d-190">También depende de la cantidad de control que desee imponer sobre los metadatos.</span><span class="sxs-lookup"><span data-stu-id="0692d-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="0692d-191">En cada nivel de la jerarquía, debe configurar etiquetas requeridas para term o TermSet.</span><span class="sxs-lookup"><span data-stu-id="0692d-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="0692d-192">Un término puede tener una o más etiquetas en el idioma predeterminado y cero o más etiquetas en el idioma no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0692d-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="0692d-193">Si el término tiene etiquetas en un idioma, una de las etiquetas debe ser la etiqueta predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0692d-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="0692d-194">**SharePoint-taxonomía: defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="0692d-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="0692d-195">Use esta etiqueta léxica predeterminada para un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que es un parámetro obligatorio para un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0692d-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="0692d-196">Se usa para representar visualmente el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0692d-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="0692d-197">La sintaxis para definir un defaultLabel es:</span><span class="sxs-lookup"><span data-stu-id="0692d-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="0692d-198">DefaultLabel contiene dos partes: la cadena y la etiqueta de idioma.</span><span class="sxs-lookup"><span data-stu-id="0692d-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="0692d-199">El idioma debe ser uno de los idiomas de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0692d-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="0692d-200">El defaultLabel debe ser único para todos los [términos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en el mismo [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en el mismo nivel jerárquico.</span><span class="sxs-lookup"><span data-stu-id="0692d-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="0692d-201">**SharePoint-taxonomía: termSetName**</span><span class="sxs-lookup"><span data-stu-id="0692d-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="0692d-202">Obtiene y establece el nombre del objeto TermSet actual.</span><span class="sxs-lookup"><span data-stu-id="0692d-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="0692d-203">Esta es la etiqueta léxica de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0692d-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="0692d-204">Se trata de un parámetro obligatorio para [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0692d-205">Se usa para representar visualmente un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="0692d-206">La sintaxis para definir un termSetName es:</span><span class="sxs-lookup"><span data-stu-id="0692d-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="0692d-207">**SharePoint-taxonomía: propertyName**</span><span class="sxs-lookup"><span data-stu-id="0692d-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="0692d-208">Obtiene y establece el nombre de propiedad para el objeto TermSet actual.</span><span class="sxs-lookup"><span data-stu-id="0692d-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="0692d-209">Esta es la etiqueta léxica de una taxonomía de SharePoint: SharedCustomPropertyForTerm, SharePoint-Taxonomy: LocalCustomPropertyForTerm y SharePoint-Taxonomy: CustomPropertyForTermSet en un idioma de trabajo de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0692d-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="0692d-210">SharePoint-Taxonomy: propertyName se trata como la clave de la CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="0692d-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="0692d-211">La sintaxis para definir un propetyName es:</span><span class="sxs-lookup"><span data-stu-id="0692d-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="0692d-212">Etiquetas opcionales</span><span class="sxs-lookup"><span data-stu-id="0692d-212">Optional labels</span></span>

<span data-ttu-id="0692d-213">También puede agregar etiquetas opcionales a su taxonomía.</span><span class="sxs-lookup"><span data-stu-id="0692d-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="0692d-214">**SharePoint-taxonomía: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="0692d-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="0692d-215">Esta es la etiqueta léxica alternativa de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0692d-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="0692d-216">La sintaxis para definir un otherLabel es:</span><span class="sxs-lookup"><span data-stu-id="0692d-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="0692d-217">Relaciones semánticas</span><span class="sxs-lookup"><span data-stu-id="0692d-217">Semantic relationships</span></span>

<span data-ttu-id="0692d-218">Las taxonomías tienen una relación asociativa jerárquica y a veces "" término relacionado ", pero algunas tienen" relaciones semánticas "o relaciones creadas de forma personalizada.</span><span class="sxs-lookup"><span data-stu-id="0692d-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="0692d-219">**SharePoint-taxonomía: principal**</span><span class="sxs-lookup"><span data-stu-id="0692d-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="0692d-220">Esta jerarquía relaciona jerárquicamente un [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) con otro [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0692d-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="0692d-221">Un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) puede ser un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nivel superior de un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), pero en caso de que no debe tener un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)primario.</span><span class="sxs-lookup"><span data-stu-id="0692d-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="0692d-222">La sintaxis para definir un elemento primario es:</span><span class="sxs-lookup"><span data-stu-id="0692d-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="0692d-223">Esto significa que TermA1 tiene el término primario.</span><span class="sxs-lookup"><span data-stu-id="0692d-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="0692d-224">Por el contrario, también significa que TermA1 es el elemento secundario de terma.</span><span class="sxs-lookup"><span data-stu-id="0692d-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="0692d-225">La relación de elementos principales y secundarios es una relación inverso.</span><span class="sxs-lookup"><span data-stu-id="0692d-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="0692d-226">**SharePoint-taxonomía: secundaria**</span><span class="sxs-lookup"><span data-stu-id="0692d-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="0692d-227">El objeto contiene una o varias instancias TermSet secundarias, y se puede tener acceso a ellas a través de la propiedad TermSets.</span><span class="sxs-lookup"><span data-stu-id="0692d-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="0692d-228">Esta clase también proporciona métodos para crear nuevos objetos TermSet secundarios.</span><span class="sxs-lookup"><span data-stu-id="0692d-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="0692d-229">Los permisos para editar las instancias de term secundario y TermSet se especifican en el grupo.</span><span class="sxs-lookup"><span data-stu-id="0692d-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="0692d-230">Esta jerarquía relaciona jerárquicamente un [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) con otro [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0692d-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="0692d-231">La sintaxis para definir un elemento secundario es:</span><span class="sxs-lookup"><span data-stu-id="0692d-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="0692d-232">Esto significa que terma tiene TermA1 secundarios.</span><span class="sxs-lookup"><span data-stu-id="0692d-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="0692d-233">Por el contrario, también significa que la relación primaria-secundaria de TermA1 es la relación inverso.</span><span class="sxs-lookup"><span data-stu-id="0692d-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="0692d-234">Notas de la documentación</span><span class="sxs-lookup"><span data-stu-id="0692d-234">Documentation notes</span></span>

<span data-ttu-id="0692d-235">En esta sección se describe la taxonomía detallada en el espacio de nombres Microsoft. SharePoint. Taxonomy.</span><span class="sxs-lookup"><span data-stu-id="0692d-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="0692d-236">**SharePoint-taxonomía: Descripción**</span><span class="sxs-lookup"><span data-stu-id="0692d-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="0692d-237">Esta es una explicación detallada de cualquier entidad de vocabulario de [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="0692d-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="0692d-238">La sintaxis para agregar una descripción es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0692d-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="0692d-239">Propiedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="0692d-239">Custom properties</span></span>

<span data-ttu-id="0692d-240">Obtiene la colección de objetos Property personalizados del objeto term actual a partir del Diccionario de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0692d-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="0692d-241">Las propiedades personalizadas son pares de valores clave que se pueden definir para un [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), para seguir la descripción del [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o de un [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0692d-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0692d-242">SharePoint especifica la clave de la propiedad personalizada con la ayuda de propertyName.</span><span class="sxs-lookup"><span data-stu-id="0692d-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="0692d-243">**SharePoint-taxonomía: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="0692d-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="0692d-244">La sintaxis para definir esto es:</span><span class="sxs-lookup"><span data-stu-id="0692d-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="0692d-245">**SharePoint-taxonomía: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="0692d-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="0692d-246">Si la propiedad personalizada de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) debe transferirse junto con el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, debe definirlo en SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="0692d-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="0692d-247">La sintaxis para definir esto es:</span><span class="sxs-lookup"><span data-stu-id="0692d-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="0692d-248">**SharePoint-taxonomía: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="0692d-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="0692d-249">Si no es necesario que la propiedad personalizada de un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) se lleve a cabo junto con el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), cuando vuelva a usar el [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) en otro lugar, deberá definirlo en LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="0692d-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="0692d-250">La sintaxis para definir esto es:</span><span class="sxs-lookup"><span data-stu-id="0692d-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="0692d-251">Propiedades de datos</span><span class="sxs-lookup"><span data-stu-id="0692d-251">Data properties</span></span>

<span data-ttu-id="0692d-252">En cada nivel de la jerarquía, puede configurar propiedades de datos específicas para un term o TermSet.</span><span class="sxs-lookup"><span data-stu-id="0692d-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="0692d-253">**SharePoint-taxonomía: isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="0692d-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="0692d-254">Use esta para especificar si un [término](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponible en listas y bibliotecas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0692d-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="0692d-255">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0692d-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="0692d-256">Dominio y intervalo</span><span class="sxs-lookup"><span data-stu-id="0692d-256">Domain and range</span></span>

<span data-ttu-id="0692d-257">En la tabla siguiente se describe el dominio y el rango de vocabulario de la taxonomía de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0692d-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="0692d-258">Predicados/verbo</span><span class="sxs-lookup"><span data-stu-id="0692d-258">Predicates/verb</span></span>|<span data-ttu-id="0692d-259">Significado</span><span class="sxs-lookup"><span data-stu-id="0692d-259">Meaning</span></span>|<span data-ttu-id="0692d-260">Dominio</span><span class="sxs-lookup"><span data-stu-id="0692d-260">Domain</span></span>|<span data-ttu-id="0692d-261">Range</span><span class="sxs-lookup"><span data-stu-id="0692d-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="0692d-262">inTermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-262">inTermSet</span></span>|<span data-ttu-id="0692d-263">En el conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="0692d-263">In term set</span></span>|<span data-ttu-id="0692d-264">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-264">Term</span></span>|<span data-ttu-id="0692d-265">Conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="0692d-265">Term Set</span></span>|
<span data-ttu-id="0692d-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="0692d-266">inTermGroup</span></span>|<span data-ttu-id="0692d-267">En el grupo de términos</span><span class="sxs-lookup"><span data-stu-id="0692d-267">In term group</span></span>|<span data-ttu-id="0692d-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-268">TermSet</span></span>|<span data-ttu-id="0692d-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="0692d-269">TermGroup</span></span>|
<span data-ttu-id="0692d-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="0692d-270">topLevelTermOf</span></span>|<span data-ttu-id="0692d-271">Es el período de nivel superior de</span><span class="sxs-lookup"><span data-stu-id="0692d-271">Is Top Level Term Of</span></span>|<span data-ttu-id="0692d-272">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-272">Term</span></span>|<span data-ttu-id="0692d-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-273">TermSet</span></span>|
<span data-ttu-id="0692d-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="0692d-274">hasTopLevelTerm</span></span>|<span data-ttu-id="0692d-275">Tiene un término de nivel superior</span><span class="sxs-lookup"><span data-stu-id="0692d-275">Has top level term</span></span>|<span data-ttu-id="0692d-276">Conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="0692d-276">Term Set</span></span>|<span data-ttu-id="0692d-277">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-277">Term</span></span>|
<span data-ttu-id="0692d-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="0692d-278">termSetName</span></span>|<span data-ttu-id="0692d-279">El conjunto de términos tiene el nombre</span><span class="sxs-lookup"><span data-stu-id="0692d-279">Term set has Name</span></span>|<span data-ttu-id="0692d-280">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-280">Term</span></span>|<span data-ttu-id="0692d-281">Literal sin formato</span><span class="sxs-lookup"><span data-stu-id="0692d-281">Plain literal</span></span>|
<span data-ttu-id="0692d-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-282">defaultLabel</span></span>|<span data-ttu-id="0692d-283">El término tiene una etiqueta predeterminada</span><span class="sxs-lookup"><span data-stu-id="0692d-283">Term has default label</span></span>|<span data-ttu-id="0692d-284">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-284">Term</span></span>|<span data-ttu-id="0692d-285">Literal sin formato</span><span class="sxs-lookup"><span data-stu-id="0692d-285">Plain literal</span></span>|
<span data-ttu-id="0692d-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="0692d-286">otherLabel</span></span>|<span data-ttu-id="0692d-287">El término tiene otra etiqueta</span><span class="sxs-lookup"><span data-stu-id="0692d-287">Term has other label</span></span>|<span data-ttu-id="0692d-288">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-288">Term</span></span>|<span data-ttu-id="0692d-289">Literal sin formato</span><span class="sxs-lookup"><span data-stu-id="0692d-289">Plain literal</span></span>|
<span data-ttu-id="0692d-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="0692d-290">propertyName</span></span>|<span data-ttu-id="0692d-291">Tiene etiqueta de propiedad</span><span class="sxs-lookup"><span data-stu-id="0692d-291">Has Property Label</span></span>|<span data-ttu-id="0692d-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="0692d-293">Boolean, String, integer, decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0692d-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="0692d-294">description</span><span class="sxs-lookup"><span data-stu-id="0692d-294">description</span></span>|<span data-ttu-id="0692d-295">Tiene una descripción</span><span class="sxs-lookup"><span data-stu-id="0692d-295">Has Description</span></span>|<span data-ttu-id="0692d-296">Todo</span><span class="sxs-lookup"><span data-stu-id="0692d-296">All</span></span>|<span data-ttu-id="0692d-297">Literal sin formato</span><span class="sxs-lookup"><span data-stu-id="0692d-297">Plain literal</span></span>|
|<span data-ttu-id="0692d-298">primario</span><span class="sxs-lookup"><span data-stu-id="0692d-298">parent</span></span>|<span data-ttu-id="0692d-299">Tiene un elemento primario</span><span class="sxs-lookup"><span data-stu-id="0692d-299">Has parent</span></span>|<span data-ttu-id="0692d-300">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-300">Term</span></span>|<span data-ttu-id="0692d-301">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-301">Term</span></span>|
|<span data-ttu-id="0692d-302">hija</span><span class="sxs-lookup"><span data-stu-id="0692d-302">child</span></span>|<span data-ttu-id="0692d-303">Tiene un elemento secundario</span><span class="sxs-lookup"><span data-stu-id="0692d-303">Has Child</span></span>|<span data-ttu-id="0692d-304">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-304">Term</span></span>|<span data-ttu-id="0692d-305">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-305">Term</span></span>|
|<span data-ttu-id="0692d-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="0692d-306">isAvailableForTagging</span></span>|<span data-ttu-id="0692d-307">Está disponible para etiquetado</span><span class="sxs-lookup"><span data-stu-id="0692d-307">Is available for tagging</span></span>|<span data-ttu-id="0692d-308">Término, conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="0692d-308">Term, Term Set</span></span>|<span data-ttu-id="0692d-309">Boolean</span><span class="sxs-lookup"><span data-stu-id="0692d-309">Boolean</span></span>|
|<span data-ttu-id="0692d-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0692d-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="0692d-311">Tiene la propiedad personalizada Shared</span><span class="sxs-lookup"><span data-stu-id="0692d-311">Has shared custom property</span></span>|<span data-ttu-id="0692d-312">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-312">Term</span></span>|<span data-ttu-id="0692d-313">Boolean, String, integer, decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0692d-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="0692d-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0692d-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="0692d-315">Tiene propiedad personalizada local</span><span class="sxs-lookup"><span data-stu-id="0692d-315">Has local custom property</span></span>|<span data-ttu-id="0692d-316">Term</span><span class="sxs-lookup"><span data-stu-id="0692d-316">Term</span></span>|<span data-ttu-id="0692d-317">Boolean, String, integer, decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0692d-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="0692d-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="0692d-319">Tiene una propiedad personalizada</span><span class="sxs-lookup"><span data-stu-id="0692d-319">Has Custom Property</span></span>|<span data-ttu-id="0692d-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="0692d-320">TermSet</span></span>|<span data-ttu-id="0692d-321">Boolean, String, integer, decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0692d-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="0692d-322">[SKOS](https://www.w3.org/TR/skos-primer/) escenarios válidos que la [taxonomía de SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) no permite:</span><span class="sxs-lookup"><span data-stu-id="0692d-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="0692d-323">Redundancia jerárquica: un concepto de [SKOS](https://www.w3.org/TR/skos-primer/) se puede adjuntar a varios conceptos más amplios al mismo tiempo, pero una taxonomía de SharePoint: Term solo puede tener una taxonomía de SharePoint: el elemento primario, por lo tanto, la dependencia cíclica, de los términos tampoco se permite.</span><span class="sxs-lookup"><span data-stu-id="0692d-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="0692d-324">Los términos huérfanos no se permiten en la taxonomía de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0692d-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="0692d-325">Cada taxonomía de SharePoint: Term debe tener una taxonomía de SharePoint: principal o bien la taxonomía de SharePoint: topLevelTermOf un TermSet.</span><span class="sxs-lookup"><span data-stu-id="0692d-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="0692d-326">La taxonomía de SharePoint no admite relaciones asociativas.</span><span class="sxs-lookup"><span data-stu-id="0692d-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="0692d-327">La taxonomía de SharePoint solo permite 2 tipos de relaciones jerárquicas: SharePoint-Taxonomy: principal y SharePoint-taxonomía: secundario.</span><span class="sxs-lookup"><span data-stu-id="0692d-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="0692d-328">A diferencia de [SKOS](https://www.w3.org/TR/skos-primer/) la relación jerárquica en el vocabulario de la taxonomía de SharePoint, solo se puede establecer con términos dentro del mismo TermSet.</span><span class="sxs-lookup"><span data-stu-id="0692d-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="0692d-329">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0692d-329">See also</span></span>

[<span data-ttu-id="0692d-330">Importar un conjunto de términos mediante un formato basado en SKOS</span><span class="sxs-lookup"><span data-stu-id="0692d-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

