---
title: Recorte de seguridad de Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Información general sobre cómo se usa la seguridad para ver temas.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939628"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="4c2e5-103">Recorte de seguridad de Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="4c2e5-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="4c2e5-104">Los usuarios de Viva Topics no pueden ver información en temas que sus permisos existentes de Office 365 les impiden ver.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="4c2e5-105">Todo lo que un usuario ve en una página de tema (por ejemplo, sitios de SharePoint, documentos, archivos) será información que ya pueden ver.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="4c2e5-106">Viva Topics no realiza cambios en ningún permiso existente.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="4c2e5-107">Por qué dos usuarios pueden tener diferentes vistas del mismo tema</span><span class="sxs-lookup"><span data-stu-id="4c2e5-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="4c2e5-108">Cuando se crea un tema a través de la IA o la curación manual, puede contener una descripción del tema, nombres alternativos, personas asociadas al tema, así como sitios, páginas y archivos relacionados con el tema.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="4c2e5-109">Cuando esta información se ve en una página de tema, es posible que dos usuarios que están viendo el mismo tema no vean la misma información.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="4c2e5-110">Por ejemplo, cuando el usuario 1 ve la página del tema Neptuno, es posible que vea esta vista de la página del tema.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Tema Neptuno para el usuario 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="4c2e5-112">Sin embargo, cuando el usuario 2 mira la misma página de tema de Neptuno, su vista difiere del usuario 1.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="4c2e5-113">El usuario 2 puede ver el archivo *DG-2000 Product Overview* en la sección Archivos anclados y páginas de la página del tema, que no aparece para el usuario 1. </span><span class="sxs-lookup"><span data-stu-id="4c2e5-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Tema de Neptuno para el usuario 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="4c2e5-115">La diferencia en lo que los usuarios pueden ver en el mismo tema es porque es posible que los usuarios no tengan los permisos de Office 365 para ver un archivo o sitio relacionado.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="4c2e5-116">Viva Topics respeta los permisos que se establecen en los elementos de un tema y no puede cambiar el acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="4c2e5-117">En nuestro ejemplo, el usuario 1 no puede ver el archivo *DG-2000 Product Overview* en su página de tema para Neptuno porque el usuario 1 no tiene permisos de Office 365 para ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="4c2e5-118">Si un usuario no puede ver suficiente información en un tema para que sea útil, el tema no estará disponible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="4c2e5-119">Cuando esto suceda, el usuario no verá el tema resaltado.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="4c2e5-120">Un usuario diferente que tenga permisos para obtener más información en el tema para que sea útil, podrá ver el tema.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="4c2e5-121">Permisos de temas para administradores de conocimientos y colaboradores de temas</span><span class="sxs-lookup"><span data-stu-id="4c2e5-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="4c2e5-122">Los usuarios a los que se les asignan permisos para administrar temas (administradores de conocimientos) solo podrán ver la información que tienen permisos para ver en los temas.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="4c2e5-123">Del mismo modo, los usuarios que tengan permisos de creación y edición de temas (colaboradores de temas) solo podrán ver la información que tienen permisos para ver en los temas.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="4c2e5-124">Información de tema de inteligencia artificial frente a la curada manualmente</span><span class="sxs-lookup"><span data-stu-id="4c2e5-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="4c2e5-125">Los temas pueden contener información generada por la inteligencia artificial y la información agregada o editada por colaboradores de temas o administradores de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="4c2e5-126">La información de un tema que AI agregó solo es visible para las personas que tienen acceso al contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="4c2e5-127">La descripción del tema y la información de personas que ha agregado o editado manualmente un colaborador del tema o un administrador de conocimientos es visible para todos los usuarios que pueden ver el tema.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="4c2e5-128">Los archivos, páginas y sitios solo son visibles para los usuarios que tienen permisos para el contenido de origen, ya sean agregados manualmente o agregados por AI.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="4c2e5-129">En la tabla siguiente se describe lo que los usuarios (visores de temas, colaboradores y administradores de conocimientos) pueden ver en un tema determinado en función de sus permisos.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="4c2e5-130">Elemento de tema</span><span class="sxs-lookup"><span data-stu-id="4c2e5-130">Topic item</span></span>|<span data-ttu-id="4c2e5-131">Qué pueden ver los usuarios</span><span class="sxs-lookup"><span data-stu-id="4c2e5-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="4c2e5-132">Nombre del tema</span><span class="sxs-lookup"><span data-stu-id="4c2e5-132">Topic name</span></span>|<span data-ttu-id="4c2e5-133">Los usuarios pueden ver el nombre del tema de los temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="4c2e5-134">Es posible que algunos temas no sean visibles si los usuarios no tienen permisos para el contenido de origen o tienen una relevancia baja para el usuario.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="4c2e5-135">Descripción del tema</span><span class="sxs-lookup"><span data-stu-id="4c2e5-135">Topic description</span></span>|<span data-ttu-id="4c2e5-136">Las descripciones generadas por IA solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="4c2e5-137">Todas las descripciones introducidas o editadas manualmente son visibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="4c2e5-138">Contactos</span><span class="sxs-lookup"><span data-stu-id="4c2e5-138">People</span></span>|<span data-ttu-id="4c2e5-139">Las personas ancladas son visibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="4c2e5-140">Las personas sugeridas solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4c2e5-141">Archivos</span><span class="sxs-lookup"><span data-stu-id="4c2e5-141">Files</span></span>|<span data-ttu-id="4c2e5-142">Los archivos solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4c2e5-143">Páginas</span><span class="sxs-lookup"><span data-stu-id="4c2e5-143">Pages</span></span>|<span data-ttu-id="4c2e5-144">Las páginas solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4c2e5-145">Sitios</span><span class="sxs-lookup"><span data-stu-id="4c2e5-145">Sites</span></span>|<span data-ttu-id="4c2e5-146">Los sitios solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="4c2e5-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="4c2e5-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c2e5-147">See also</span></span>

