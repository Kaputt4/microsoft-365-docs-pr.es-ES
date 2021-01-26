---
title: 'Administrar temas en el Centro de temas en Experiencias de temas (versión preliminar) '
description: Cómo administrar temas en el Centro de temas.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 371ccc16e787b331f42026dec48e5e3113b2b172
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976196"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="db17c-103">Administrar temas en el Centro de temas (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="db17c-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="db17c-104">El contenido de este artículo es para Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="db17c-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="db17c-105">[Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="db17c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="db17c-106">En el Centro de temas,  un administrador de conocimientos puede ver la página Administrar temas para revisar los temas que se han identificado en ubicaciones de origen de SharePoint según lo especificado por su administrador de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="db17c-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Centro de temas](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="db17c-108">Los administradores de conocimientos ayudan a guiar los temas detectados durante el ciclo de vida de los temas en los que se incluyen los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="db17c-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="db17c-109">Sugerido: Un tema ha sido identificado por la inteligencia artificial y tiene suficientes recursos, conexiones y propiedades compatibles para cumplir el umbral del tema.</span><span class="sxs-lookup"><span data-stu-id="db17c-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="db17c-110">Confirmado: se valida un tema sugerido por AI.</span><span class="sxs-lookup"><span data-stu-id="db17c-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="db17c-111">La validación se realiza mediante la confirmación de un administrador de conocimientos. Además, se puede confirmar un tema si al menos dos usuarios dan comentarios positivos a través de comentarios sobre el tema que el tema es válido.</span><span class="sxs-lookup"><span data-stu-id="db17c-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="db17c-112">Eliminado: un administrador de conocimientos rechaza un tema y ya no será visible para los espectadores.</span><span class="sxs-lookup"><span data-stu-id="db17c-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="db17c-113">El tema puede estar en cualquier estado cuando se quita (sugerido o confirmado).</span><span class="sxs-lookup"><span data-stu-id="db17c-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="db17c-114">Publicado: un tema confirmado que se ha actualizado manualmente.</span><span class="sxs-lookup"><span data-stu-id="db17c-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Gráfico de ciclo de vida de temas](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="db17c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db17c-116">Requirements</span></span>

<span data-ttu-id="db17c-117">Para administrar temas en el Centro de temas, debe:</span><span class="sxs-lookup"><span data-stu-id="db17c-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="db17c-118">Tener una licencia de Experiencias de tema.</span><span class="sxs-lookup"><span data-stu-id="db17c-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="db17c-119">Tener permisos para quién [**puede administrar temas.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)</span><span class="sxs-lookup"><span data-stu-id="db17c-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="db17c-120">Los administradores de conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema de Knowledge Network.</span><span class="sxs-lookup"><span data-stu-id="db17c-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="db17c-121">No podrá ver la página Administrar temas en el Centro de temas a menos que tenga el permiso **Quién puede administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="db17c-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="db17c-122">En el centro de temas, un administrador de conocimientos puede revisar los temas que se han identificado en las ubicaciones de origen de SharePoint que especificó y puede confirmarlos o rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="db17c-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="db17c-123">Un administrador de conocimientos también puede crear y publicar nuevas páginas de temas si no se encontró una en la detección de temas o editar las existentes si es necesario actualizarlas.</span><span class="sxs-lookup"><span data-stu-id="db17c-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="db17c-124">Revisar los temas sugeridos</span><span class="sxs-lookup"><span data-stu-id="db17c-124">Review suggested topics</span></span>

<span data-ttu-id="db17c-125">En la página Administrar temas del Centro de temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas aparecerán en la **pestaña Sugerencias.** Un administrador de conocimientos puede revisar los temas no confirmados y elegir confirmarlos o rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="db17c-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="db17c-126">Para revisar un tema sugerido:</span><span class="sxs-lookup"><span data-stu-id="db17c-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="db17c-127">En la **página Administrar temas,** seleccione la **pestaña Sugerencias** y seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="db17c-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="db17c-128">En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="db17c-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="db17c-129">Después de revisar el tema, vuelva a la página Administrar temas.</span><span class="sxs-lookup"><span data-stu-id="db17c-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="db17c-130">Para el tema seleccionado, puede:</span><span class="sxs-lookup"><span data-stu-id="db17c-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="db17c-131">Seleccione la marca de verificación para confirmar el tema.</span><span class="sxs-lookup"><span data-stu-id="db17c-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="db17c-132">Seleccione la **x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="db17c-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="db17c-133">Los temas confirmados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **lista Confirmados.**</span><span class="sxs-lookup"><span data-stu-id="db17c-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="db17c-134">Los temas rechazados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **pestaña** Quitado.</span><span class="sxs-lookup"><span data-stu-id="db17c-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="db17c-135">Temas confirmados</span><span class="sxs-lookup"><span data-stu-id="db17c-135">Confirmed topics</span></span>

<span data-ttu-id="db17c-136">En la página Administrar temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas y que un administrador de  conocimientos confirmó o que confirmaron dos o más personas a través del mecanismo de comentarios de la tarjeta aparecerán en la pestaña Confirmado. Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="db17c-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="db17c-137">Para revisar un tema confirmado:</span><span class="sxs-lookup"><span data-stu-id="db17c-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="db17c-138">En la **pestaña Confirmado,** seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="db17c-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="db17c-139">En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="db17c-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="db17c-140">Tenga en cuenta que aún puede optar por rechazar un tema confirmado.</span><span class="sxs-lookup"><span data-stu-id="db17c-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="db17c-141">Para ello, vaya al tema seleccionado en la lista Confirmados y seleccione la **x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="db17c-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="db17c-142">Temas publicados</span><span class="sxs-lookup"><span data-stu-id="db17c-142">Published topics</span></span>
<span data-ttu-id="db17c-143">Los temas publicados se han editado para que siempre aparezca información específica para los usuarios que encuentren la página.</span><span class="sxs-lookup"><span data-stu-id="db17c-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="db17c-144">Los temas creados manualmente se enumeran aquí.</span><span class="sxs-lookup"><span data-stu-id="db17c-144">Manually created topics are listed here.</span></span>




