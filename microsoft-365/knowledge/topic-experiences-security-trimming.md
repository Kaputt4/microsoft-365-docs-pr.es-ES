---
title: El tema experimenta el recorte de seguridad (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Información general sobre cómo se usa la seguridad para ver temas.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699060"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="5e7a4-103">El tema experimenta el recorte de seguridad (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e7a4-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="5e7a4-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="5e7a4-105">[Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="5e7a4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="5e7a4-106">El tema experiencias de los usuarios no podrá ver información en los temas que los permisos de Office 365 existentes impiden que se vean.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="5e7a4-107">Todo lo que un usuario ve en una página de tema (por ejemplo, sitios de SharePoint, documentos, archivos) será la información que ya se permite ver.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="5e7a4-108">El tema experiencias no realiza cambios en los permisos existentes.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="5e7a4-109">Por qué dos usuarios pueden tener diferentes vistas del mismo tema</span><span class="sxs-lookup"><span data-stu-id="5e7a4-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="5e7a4-110">Cuando se crea un tema mediante AI o curation manual, puede incluir una descripción del tema, nombres alternativos, personas asociadas con el tema, así como sitios, páginas y archivos relacionados con el tema.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="5e7a4-111">Cuando esta información se muestra en una página de tema, es posible que dos usuarios que estén viendo el mismo tema no vean la misma información.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="5e7a4-112">Por ejemplo, cuando el usuario 1 ve la página del tema Neptune, esto es lo que pueden ver.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![Tema de Neptune para el usuario 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="5e7a4-114">Sin embargo, cuando el usuario 2 mira la misma página del tema de Neptune, su vista difiere del usuario 1.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="5e7a4-115">El usuario 2 puede ver el archivo de *información general del producto DG-2000* en la sección **archivos y páginas ancladas** de la página del tema, que no aparece para el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Tema de Neptune para el usuario 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="5e7a4-117">La diferencia en lo que los usuarios pueden ver en el mismo tema es porque es posible que los usuarios no dispongan de los permisos de Office 365 para ver un archivo o sitio relacionado.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="5e7a4-118">El tema experiencias respeta los permisos que se establecen en los elementos de un tema y no puede cambiar el acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="5e7a4-119">En nuestro ejemplo, el usuario 1 no puede ver el archivo de *información general del producto DG-2000* en su página del tema para Neptune porque el usuario 1 no tiene permisos de Office 365 para ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="5e7a4-120">Si un usuario no puede ver suficiente información en un tema para que resulte útil, el tema no estará disponible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="5e7a4-121">En este caso, el usuario no verá el tema resaltado.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="5e7a4-122">Sin embargo, un usuario distinto que tenga permisos para obtener más información en el tema para que sea útil, podrá ver el tema.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="5e7a4-123">Tema permisos para administradores del conocimiento y colaboradores del tema</span><span class="sxs-lookup"><span data-stu-id="5e7a4-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="5e7a4-124">Usuarios a los que se les han asignado permisos para administrar temas: administradores de conocimiento: solo podrán ver la información que tienen permisos para ver en los temas.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="5e7a4-125">De forma similar, los usuarios que tienen permisos para crear y editar temas: colaboradores de tema solo podrán ver la información que tienen permisos para ver en los temas.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="5e7a4-126">AI frente a información del tema de creados manual</span><span class="sxs-lookup"><span data-stu-id="5e7a4-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="5e7a4-127">Los temas pueden contener información generada por AI e información agregada o modificada por los colaboradores de temas o los administradores de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="5e7a4-128">La información de un tema agregado por AI solo es visible para los usuarios que tienen acceso al contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="5e7a4-129">La información que se ha agregado o editado manualmente por un colaborador de temas o por el administrador de conocimiento es visible para todos los usuarios que puedan ver el tema.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="5e7a4-130">En la tabla siguiente, se describen los visores de temas, los colaboradores y los administradores del conocimiento que pueden ver en un tema determinado en función de sus permisos.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="5e7a4-131">Elemento de tema</span><span class="sxs-lookup"><span data-stu-id="5e7a4-131">Topic item</span></span>|<span data-ttu-id="5e7a4-132">Qué pueden ver los usuarios</span><span class="sxs-lookup"><span data-stu-id="5e7a4-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="5e7a4-133">Nombre del tema</span><span class="sxs-lookup"><span data-stu-id="5e7a4-133">Topic name</span></span>|<span data-ttu-id="5e7a4-134">Los usuarios pueden ver el nombre de tema de todos los temas del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="5e7a4-135">Es posible que algunos temas no estén visibles si tienen una importancia baja para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="5e7a4-136">Descripción del tema</span><span class="sxs-lookup"><span data-stu-id="5e7a4-136">Topic description</span></span>|<span data-ttu-id="5e7a4-137">Las descripciones generadas por AI solo son visibles para los usuarios que tienen permisos en el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="5e7a4-138">Las descripciones especificadas o editadas manualmente son visibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="5e7a4-139">Personas</span><span class="sxs-lookup"><span data-stu-id="5e7a4-139">People</span></span>|<span data-ttu-id="5e7a4-140">Las personas ancladas son visibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="5e7a4-141">Los usuarios sugeridos solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="5e7a4-142">Archivos</span><span class="sxs-lookup"><span data-stu-id="5e7a4-142">Files</span></span>|<span data-ttu-id="5e7a4-143">Los archivos solo están visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="5e7a4-144">Páginas</span><span class="sxs-lookup"><span data-stu-id="5e7a4-144">Pages</span></span>|<span data-ttu-id="5e7a4-145">Las páginas solo están visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="5e7a4-146">Sitios</span><span class="sxs-lookup"><span data-stu-id="5e7a4-146">Sites</span></span>|<span data-ttu-id="5e7a4-147">Los sitios solo están visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="5e7a4-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e7a4-148">See also</span></span>

