---
title: 'Administrar temas en el centro de temas de experiencias de temas (vista previa) '
description: Cómo administrar temas en el centro de temas.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 832067d157ed9ffcba1ed9ad514c375cbbdd752b
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699030"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="00cee-103">Administrar temas en el centro de temas (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="00cee-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="00cee-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="00cee-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="00cee-105">[Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="00cee-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="00cee-106">En el centro de temas, un administrador de información puede ver la página **administrar temas** para revisar los temas que se han identificado en ubicaciones de origen de SharePoint según lo especificado por su administrador de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="00cee-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Centro de temas](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="00cee-108">Los administradores de conocimientos ayudan a guiar los temas detectados a través del ciclo de vida del tema en el que los temas son:</span><span class="sxs-lookup"><span data-stu-id="00cee-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="00cee-109">Sugerido: un tema ha sido identificado por AI y tiene suficientes recursos, conexiones y propiedades auxiliares para cumplir el umbral del tema.</span><span class="sxs-lookup"><span data-stu-id="00cee-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="00cee-110">Confirmado: se valida un tema sugerido por AI.</span><span class="sxs-lookup"><span data-stu-id="00cee-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="00cee-111">La validación se realiza mediante la confirmación de un administrador de conocimiento. Además, se puede confirmar un tema si al menos dos usuarios proporcionan comentarios positivos a través de comentarios de temas que el tema es válido.</span><span class="sxs-lookup"><span data-stu-id="00cee-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="00cee-112">Quitado: un administrador de conocimiento ha rechazado un tema y ya no será visible para los visores.</span><span class="sxs-lookup"><span data-stu-id="00cee-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="00cee-113">El tema puede estar en cualquier estado cuando se quita (se sugiere o confirma).</span><span class="sxs-lookup"><span data-stu-id="00cee-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="00cee-114">Publicado: un tema confirmado que se ha actualizado manualmente.</span><span class="sxs-lookup"><span data-stu-id="00cee-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Gráfico de ciclo de vida del tema](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="00cee-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00cee-116">Requirements</span></span>

<span data-ttu-id="00cee-117">Para administrar temas en el centro de temas, debe:</span><span class="sxs-lookup"><span data-stu-id="00cee-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="00cee-118">Tener un tema de licencia de experiencia.</span><span class="sxs-lookup"><span data-stu-id="00cee-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="00cee-119">Tiene permisos para los [**usuarios que pueden administrar temas**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span><span class="sxs-lookup"><span data-stu-id="00cee-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="00cee-120">Los administradores de conocimiento pueden conceder a los usuarios este permiso en la configuración de permisos de temas de red de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="00cee-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="00cee-121">No podrá ver la página Administrar temas en el centro de temas a menos que tenga el permiso **quién puede administrar temas** .</span><span class="sxs-lookup"><span data-stu-id="00cee-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="00cee-122">En el centro de temas, un administrador de información puede revisar los temas que se han identificado en las ubicaciones de origen de SharePoint especificadas y puede confirmarlos o rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="00cee-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="00cee-123">Un administrador de información también puede crear y publicar nuevas páginas de temas si no se encuentra ninguna en la detección de temas, o editar las existentes si es necesario actualizarlas.</span><span class="sxs-lookup"><span data-stu-id="00cee-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="00cee-124">Revisión de temas sugeridos</span><span class="sxs-lookup"><span data-stu-id="00cee-124">Review suggested topics</span></span>

<span data-ttu-id="00cee-125">En la página centro de temas de administración de temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas se enumerarán en la pestaña **sugerido** . Un administrador de información puede revisar los temas no confirmados y elegir confirmarlos o rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="00cee-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="00cee-126">Para revisar un tema sugerido:</span><span class="sxs-lookup"><span data-stu-id="00cee-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="00cee-127">En la página **administrar temas** , seleccione la pestaña **sugerido** , seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="00cee-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="00cee-128">En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="00cee-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="00cee-129">Después de revisar el tema, vuelva a la página Administrar temas.</span><span class="sxs-lookup"><span data-stu-id="00cee-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="00cee-130">Para el tema seleccionado, puede:</span><span class="sxs-lookup"><span data-stu-id="00cee-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="00cee-131">Seleccione la marca de verificación para confirmar el tema.</span><span class="sxs-lookup"><span data-stu-id="00cee-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="00cee-132">Seleccione la **x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="00cee-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="00cee-133">Los temas confirmados se quitarán de la lista de **sugerencias** y ahora se mostrarán en la lista **confirmada** .</span><span class="sxs-lookup"><span data-stu-id="00cee-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="00cee-134">Los temas rechazados se quitarán de la lista **sugerida** y ahora se mostrarán en la pestaña **eliminado** .</span><span class="sxs-lookup"><span data-stu-id="00cee-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="00cee-135">Temas confirmados</span><span class="sxs-lookup"><span data-stu-id="00cee-135">Confirmed topics</span></span>

<span data-ttu-id="00cee-136">En la página Administrar temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas y que han sido confirmados por un administrador de conocimiento o "multitud de multitudes" confirmados por dos o más personas a través del mecanismo de comentarios de tarjetas se enumerarán en la pestaña **confirmada** . Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="00cee-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="00cee-137">Para revisar un tema confirmado:</span><span class="sxs-lookup"><span data-stu-id="00cee-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="00cee-138">En la pestaña **confirmada** , seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="00cee-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="00cee-139">En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="00cee-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="00cee-140">Tenga en cuenta que todavía puede rechazar un tema confirmado.</span><span class="sxs-lookup"><span data-stu-id="00cee-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="00cee-141">Para ello, vaya al tema seleccionado en la lista confirmada y seleccione la **x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="00cee-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="00cee-142">Temas publicados</span><span class="sxs-lookup"><span data-stu-id="00cee-142">Published topics</span></span>
<span data-ttu-id="00cee-143">Se han editado los temas publicados para que la información específica aparezca siempre a quien encuentre la página.</span><span class="sxs-lookup"><span data-stu-id="00cee-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="00cee-144">Aquí se muestran los temas creados manualmente.</span><span class="sxs-lookup"><span data-stu-id="00cee-144">Manually created topics are listed here.</span></span>




