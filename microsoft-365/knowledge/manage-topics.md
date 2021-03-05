---
title: Administrar temas en el Centro de temas en Temas de Microsoft Viva
description: Cómo administrar temas en el Centro de temas.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 3d083537f3a9337d88d63861e0bf66867f558aba
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454010"
---
# <a name="manage-topics-in-the-topic-center"></a><span data-ttu-id="6088e-103">Administrar temas en el Centro de temas</span><span class="sxs-lookup"><span data-stu-id="6088e-103">Manage topics in the Topic center</span></span> 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="6088e-104">En el Centro de temas de Viva, un administrador de conocimientos puede ver la página Administrar temas para revisar los temas que se han identificado en ubicaciones de origen de SharePoint según lo especificado por el administrador de conocimientos. </span><span class="sxs-lookup"><span data-stu-id="6088e-104">In the Viva Topics Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Centro de temas](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="6088e-106">Los administradores de conocimientos ayudan a guiar los temas descubiertos a través del ciclo de vida del tema en el que los temas son:</span><span class="sxs-lookup"><span data-stu-id="6088e-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="6088e-107">Sugerido: AI ha identificado un tema y tiene suficientes recursos, conexiones y propiedades compatibles.</span><span class="sxs-lookup"><span data-stu-id="6088e-107">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="6088e-108">Confirmado: se valida un tema sugerido por AI.</span><span class="sxs-lookup"><span data-stu-id="6088e-108">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="6088e-109">La validación se realiza mediante confirmación de un administrador de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="6088e-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="6088e-110">Además, se puede confirmar un tema si al menos dos usuarios dan comentarios positivos a través de la pregunta de comentarios en la tarjeta del tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="6088e-111">Publicado: Un tema confirmado que se ha seleccionado: se han realizado ediciones manuales para mejorar su calidad.</span><span class="sxs-lookup"><span data-stu-id="6088e-111">Published: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="6088e-112">Eliminado: un administrador de conocimientos rechaza un tema y ya no será visible para los visores.</span><span class="sxs-lookup"><span data-stu-id="6088e-112">Removed: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="6088e-113">El tema puede estar en cualquier estado cuando se quita (sugerido, confirmado o publicado).</span><span class="sxs-lookup"><span data-stu-id="6088e-113">The topic can be in any state when it is removed (suggested, confirmed or published).</span></span> <span data-ttu-id="6088e-114">Cuando se quita un tema publicado, la página con los detalles seleccionados tendrá que eliminarse manualmente a través de la Biblioteca de páginas del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="6088e-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![Gráfico de ciclo de vida de temas](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="6088e-116">En la página Administrar temas, cada administrador de conocimientos solo podrá ver los temas en los que tienen acceso a los archivos y páginas del tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-116">In the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="6088e-117">Esto se reflejará en los temas que se enumeran en las pestañas Sugerido, Confirmado, Eliminado y Publicado.</span><span class="sxs-lookup"><span data-stu-id="6088e-117">This will be reflected in the topics that are listed under the Suggested, Confirmed, Removed, and Published tabs.</span></span> <span data-ttu-id="6088e-118">Sin embargo, los recuentos de temas muestran los recuentos totales de la organización.</span><span class="sxs-lookup"><span data-stu-id="6088e-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="6088e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6088e-119">Requirements</span></span>

<span data-ttu-id="6088e-120">Para administrar temas en el Centro de temas, debe:</span><span class="sxs-lookup"><span data-stu-id="6088e-120">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="6088e-121">Tener una licencia de Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="6088e-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="6088e-122">Tener el [**permiso Quién puede administrar temas.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)</span><span class="sxs-lookup"><span data-stu-id="6088e-122">Have the [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) permission.</span></span> <span data-ttu-id="6088e-123">Los administradores de conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema Temas de Viva.</span><span class="sxs-lookup"><span data-stu-id="6088e-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="6088e-124">No podrá ver la página Administrar temas en el Centro de temas a menos que tenga el permiso **Quién puede administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="6088e-124">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="6088e-125">En el centro de temas, un administrador de conocimientos puede revisar los temas que se han identificado en las ubicaciones de origen de SharePoint que especificó y puede confirmarlos o rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="6088e-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="6088e-126">Un administrador de conocimientos también puede crear y publicar nuevas páginas de temas si no se encontró una en la detección de temas o editar las existentes si es necesario actualizarlas.</span><span class="sxs-lookup"><span data-stu-id="6088e-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="6088e-127">Revisar temas sugeridos</span><span class="sxs-lookup"><span data-stu-id="6088e-127">Review suggested topics</span></span>

<span data-ttu-id="6088e-128">En la página Administrar temas del centro de temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas aparecerán en la **pestaña Sugerencias.** Si es necesario, un administrador de conocimientos puede revisar temas no confirmados y elegir confirmarlos o rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="6088e-128">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![Temas sugeridos](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="6088e-130">Para revisar un tema sugerido:</span><span class="sxs-lookup"><span data-stu-id="6088e-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="6088e-131">En la **página Administrar temas,** seleccione la **pestaña Sugerencia** y seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="6088e-132">En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="6088e-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="6088e-133">La publicación de cualquier modificación moverá este tema a la **pestaña Publicado.**</span><span class="sxs-lookup"><span data-stu-id="6088e-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="6088e-134">Después de revisar el tema, vuelva a la página Administrar temas.</span><span class="sxs-lookup"><span data-stu-id="6088e-134">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="6088e-135">Para el tema seleccionado, puede:</span><span class="sxs-lookup"><span data-stu-id="6088e-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="6088e-136">Seleccione la marca de verificación para confirmar el tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="6088e-137">Seleccione la **x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="6088e-138">Los temas confirmados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **lista** Confirmados.</span><span class="sxs-lookup"><span data-stu-id="6088e-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="6088e-139">Los temas rechazados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **pestaña Eliminado.**</span><span class="sxs-lookup"><span data-stu-id="6088e-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="6088e-140">Puntuación de calidad</span><span class="sxs-lookup"><span data-stu-id="6088e-140">Quality score</span></span>

<span data-ttu-id="6088e-141">Cada tema que aparece en la página Temas sugeridos tiene asignada una <b>puntuación</b> de calidad.</span><span class="sxs-lookup"><span data-stu-id="6088e-141">Each topic that appears in your Suggested Topics page has a <b>Quality</b> score assigned to it.</span></span> <span data-ttu-id="6088e-142">La puntuación de calidad es un reflejo de la cantidad de información que el usuario promedio verá para la información sobre el tema, teniendo en cuenta que cada usuario puede ver más o menos información debido a los permisos que puede o no tener en la información de un tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-142">The Quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user may see more or less information because of the permissions they may or may not have on the information in a topic.</span></span> 

<span data-ttu-id="6088e-143">La puntuación de calidad puede ayudar a proporcionar información sobre los temas con más información y puede ser útil para encontrar temas que pueden necesitar editarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="6088e-143">The Quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span>  <span data-ttu-id="6088e-144">Por ejemplo, un tema con una puntuación de calidad inferior puede ser el resultado de que algunos usuarios no tengan permisos de SharePoint para los archivos o sitios pertinentes que AI ha incluido en el tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-144">For example, a topic with a lower quality score may be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="6088e-145">A continuación, un colaborador podría editar el tema para incluir la información (cuando corresponda), que, a continuación, se podrá ver para todos los usuarios que puedan ver el tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="6088e-146">La puntuación de calidad puede oscilar entre 1 y 100.</span><span class="sxs-lookup"><span data-stu-id="6088e-146">The Quality score could range from 1 to 100.</span></span> <span data-ttu-id="6088e-147">Un tema recién descubierto tendrá una puntuación de calidad de 0 hasta que dos o más usuarios lo han visto.</span><span class="sxs-lookup"><span data-stu-id="6088e-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="6088e-148">Cada puntuación de calidad de los usuarios viene determinada por una serie de factores, como la cantidad de contenido que se muestra para el usuario específico, que se controla los permisos del usuario, ya que cada página de tema tiene el recorte de seguridad en su lugar para el contenido generado por la IA.</span><span class="sxs-lookup"><span data-stu-id="6088e-148">Each users quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="6088e-149">La puntuación de calidad que se muestra en la pestaña Temas sugeridos es un promedio de cada puntuación individual de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6088e-149">The Quality score shown on the Suggested topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="6088e-150">Impresiones</span><span class="sxs-lookup"><span data-stu-id="6088e-150">Impressions</span></span>

<span data-ttu-id="6088e-151">La <b>columna Impresiones</b> muestra el número de veces que se ha mostrado un tema a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="6088e-151">The <b>Impressions</b> column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="6088e-152">Esto incluye vistas a través de tarjetas de tema en la búsqueda, a través de los resaltados de temas y a través de las vistas del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="6088e-152">This includes views through topic cards in search, through topic highlights, and through Topic center views.</span></span> <span data-ttu-id="6088e-153">No refleja el clic en estos temas, sino que se ha mostrado el tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="6088e-154">La columna Impresiones se mostrará para los temas de las pestañas Sugeridos, Confirmados, Publicados y Eliminados de la página Administrar temas.</span><span class="sxs-lookup"><span data-stu-id="6088e-154">The Impressions column will show for topics in the Suggested, Confirmed, Published, and Removed tabs in the Manage Topics page.</span></span>


## <a name="confirmed-topics"></a><span data-ttu-id="6088e-155">Temas confirmados</span><span class="sxs-lookup"><span data-stu-id="6088e-155">Confirmed topics</span></span>

<span data-ttu-id="6088e-156">En la página Administrar temas, los temas detectados en las ubicaciones de origen de SharePoint especificadas y confirmados por un administrador de  conocimientos o "origen de personas" confirmados por dos o más personas a través del mecanismo de comentarios de tarjeta se mostrarán en la pestaña Confirmado. Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="6088e-156">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="6088e-157">Para revisar un tema confirmado:</span><span class="sxs-lookup"><span data-stu-id="6088e-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="6088e-158">En la **pestaña Confirmado,** seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="6088e-159">En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="6088e-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="6088e-160">Tenga en cuenta que aún puede optar por rechazar un tema confirmado.</span><span class="sxs-lookup"><span data-stu-id="6088e-160">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="6088e-161">Para ello, vaya al tema seleccionado en la lista Confirmado y seleccione **la x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="6088e-161">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="6088e-162">Temas publicados</span><span class="sxs-lookup"><span data-stu-id="6088e-162">Published topics</span></span>
<span data-ttu-id="6088e-163">Los temas publicados se han editado para que la información específica siempre aparezca a quien encuentre la página.</span><span class="sxs-lookup"><span data-stu-id="6088e-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="6088e-164">Aquí también se enumeran los temas creados manualmente.</span><span class="sxs-lookup"><span data-stu-id="6088e-164">Manually created topics are listed here as well.</span></span>

   ![Administrar temas](../media/knowledge-management/manage-topics-new.png) </br> 




