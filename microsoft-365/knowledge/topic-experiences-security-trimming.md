---
title: Recorte de seguridad de Temas de Microsoft Viva
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
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107523"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="cad2a-103">Recorte de seguridad de Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="cad2a-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="cad2a-104">Los usuarios de Temas Viva no pueden ver información en temas que sus permisos de Office 365 existentes les impiden ver.</span><span class="sxs-lookup"><span data-stu-id="cad2a-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="cad2a-105">Todo lo que un usuario ve en una página de tema (por ejemplo, sitios de SharePoint, documentos, archivos) será información que ya pueden ver.</span><span class="sxs-lookup"><span data-stu-id="cad2a-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="cad2a-106">Temas de Viva no realiza cambios en los permisos existentes.</span><span class="sxs-lookup"><span data-stu-id="cad2a-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="cad2a-107">Por qué dos usuarios pueden tener distintas vistas del mismo tema</span><span class="sxs-lookup"><span data-stu-id="cad2a-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="cad2a-108">Cuando se crea un tema a través de la IA o la conservación manual, puede contener una descripción del tema, nombres alternativos, personas asociadas al tema, así como sitios, páginas y archivos relacionados con el tema.</span><span class="sxs-lookup"><span data-stu-id="cad2a-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="cad2a-109">Cuando esta información se ve en una página de tema, es posible que dos usuarios que están viendo el mismo tema no vean la misma información.</span><span class="sxs-lookup"><span data-stu-id="cad2a-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="cad2a-110">Por ejemplo, cuando el usuario 1 ve la página del tema Descúes, es posible que vea esta vista de la página del tema.</span><span class="sxs-lookup"><span data-stu-id="cad2a-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Tema sobre el tema Desc( para el usuario 1)](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="cad2a-112">Sin embargo, cuando el usuario 2 mira la misma página del tema Desfila, su vista difiere del usuario 1.</span><span class="sxs-lookup"><span data-stu-id="cad2a-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="cad2a-113">El usuario 2 puede ver el archivo *DG-2000 Product Overview* en la sección de páginas y archivos anclados de la página de tema, que no aparece para el usuario 1. </span><span class="sxs-lookup"><span data-stu-id="cad2a-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Tema sobre el tema Desc( para el usuario 2)](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="cad2a-115">La diferencia en lo que los usuarios pueden ver en el mismo tema se debe a que es posible que los usuarios no tengan los permisos de Office 365 para ver un archivo o sitio relacionado.</span><span class="sxs-lookup"><span data-stu-id="cad2a-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="cad2a-116">Viva Topics respeta los permisos establecidos en los elementos de un tema y no puede cambiar el acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="cad2a-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="cad2a-117">En nuestro ejemplo, el usuario 1 no puede ver el archivo *DG-2000 Información* general del producto en su página de tema para Larión porque el usuario 1 no tiene permisos de Office 365 para ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="cad2a-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="cad2a-118">Si un usuario no puede ver suficiente información en un tema para que sea útil, el tema no estará disponible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="cad2a-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="cad2a-119">Cuando esto sucede, el usuario no verá el tema resaltado.</span><span class="sxs-lookup"><span data-stu-id="cad2a-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="cad2a-120">Un usuario diferente que tenga permisos para obtener más información en el tema para que sea útil, podrá ver el tema.</span><span class="sxs-lookup"><span data-stu-id="cad2a-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="cad2a-121">Permisos de tema para administradores de conocimientos y colaboradores de temas</span><span class="sxs-lookup"><span data-stu-id="cad2a-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="cad2a-122">Los usuarios a los que se les asignan permisos para administrar temas (administradores de conocimientos) solo podrán ver la información que tienen permisos para ver en los temas.</span><span class="sxs-lookup"><span data-stu-id="cad2a-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="cad2a-123">De forma similar, los usuarios que tienen permisos de creación y edición de temas (colaboradores de temas) solo podrán ver la información que tienen permisos para ver dentro de los temas.</span><span class="sxs-lookup"><span data-stu-id="cad2a-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="cad2a-124">Información de temas de inteligencia artificial frente a temas seleccionados manualmente</span><span class="sxs-lookup"><span data-stu-id="cad2a-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="cad2a-125">Los temas pueden contener información generada por IA e información agregada o editada por colaboradores de temas o administradores de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="cad2a-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="cad2a-126">La información de un tema que AI agregó solo es visible para las personas que tienen acceso al contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="cad2a-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="cad2a-127">La información que un colaborador o un administrador de conocimientos ha agregado o editado manualmente es visible para todos los usuarios que pueden ver el tema.</span><span class="sxs-lookup"><span data-stu-id="cad2a-127">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="cad2a-128">En la tabla siguiente se describe lo que los usuarios (visores de temas, colaboradores y administradores de conocimientos) pueden ver en un tema determinado en función de sus permisos.</span><span class="sxs-lookup"><span data-stu-id="cad2a-128">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="cad2a-129">Elemento de tema</span><span class="sxs-lookup"><span data-stu-id="cad2a-129">Topic item</span></span>|<span data-ttu-id="cad2a-130">Qué pueden ver los usuarios</span><span class="sxs-lookup"><span data-stu-id="cad2a-130">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="cad2a-131">Nombre del tema</span><span class="sxs-lookup"><span data-stu-id="cad2a-131">Topic name</span></span>|<span data-ttu-id="cad2a-132">Los usuarios pueden ver el nombre del tema de todos los temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="cad2a-132">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="cad2a-133">Es posible que algunos temas no sean visibles si tienen una relevancia baja para el usuario.</span><span class="sxs-lookup"><span data-stu-id="cad2a-133">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="cad2a-134">Descripción del tema</span><span class="sxs-lookup"><span data-stu-id="cad2a-134">Topic description</span></span>|<span data-ttu-id="cad2a-135">Las descripciones generadas por IA solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="cad2a-135">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="cad2a-136">Todas las descripciones introducidas o editadas manualmente son visibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cad2a-136">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="cad2a-137">Contactos</span><span class="sxs-lookup"><span data-stu-id="cad2a-137">People</span></span>|<span data-ttu-id="cad2a-138">Los usuarios anclados son visibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cad2a-138">Pinned people are visible to all users.</span></span> <span data-ttu-id="cad2a-139">Las personas sugeridas solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="cad2a-139">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="cad2a-140">Archivos</span><span class="sxs-lookup"><span data-stu-id="cad2a-140">Files</span></span>|<span data-ttu-id="cad2a-141">Los archivos solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="cad2a-141">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="cad2a-142">Páginas</span><span class="sxs-lookup"><span data-stu-id="cad2a-142">Pages</span></span>|<span data-ttu-id="cad2a-143">Las páginas solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="cad2a-143">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="cad2a-144">Sitios</span><span class="sxs-lookup"><span data-stu-id="cad2a-144">Sites</span></span>|<span data-ttu-id="cad2a-145">Los sitios solo son visibles para los usuarios que tienen permisos para el contenido de origen.</span><span class="sxs-lookup"><span data-stu-id="cad2a-145">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="cad2a-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cad2a-146">See also</span></span>

