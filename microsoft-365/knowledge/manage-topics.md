---
title: Administrar temas en el centro de temas en Temas de Microsoft Viva
description: Cómo administrar temas en el centro de temas.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2c29cdb6823e695cb9c96a4f51ef7b1c41642ac9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333631"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="1af53-103">Administrar temas en el centro de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="1af53-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="1af53-104">En el Centro de temas de Viva  Topics, un administrador de conocimientos puede ver la página Administrar temas para revisar los temas que se han identificado en las ubicaciones de origen según lo especificado por el administrador de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="1af53-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Centro de temas](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="1af53-106">Fases del tema</span><span class="sxs-lookup"><span data-stu-id="1af53-106">Topic stages</span></span>

<span data-ttu-id="1af53-107">Los administradores de conocimientos ayudan a guiar los temas detectados a través de las distintas fases del ciclo de vida del tema: **Sugerido** **,** **Confirmado**, Publicado y **Eliminado.**</span><span class="sxs-lookup"><span data-stu-id="1af53-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Gráfico de ciclo de vida de temas](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="1af53-109">**Sugerido:** AI ha identificado un tema y tiene suficientes recursos, conexiones y propiedades compatibles.</span><span class="sxs-lookup"><span data-stu-id="1af53-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="1af53-110">(Se marcan como **un tema sugerido** en la interfaz de usuario).</span><span class="sxs-lookup"><span data-stu-id="1af53-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="1af53-111">**Confirmado:** se valida un tema sugerido por AI.</span><span class="sxs-lookup"><span data-stu-id="1af53-111">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="1af53-112">Un administrador de conocimientos debe confirmar la validación del tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-112">Topic validation must be confirmed by a knowledge manager.</span></span> <span data-ttu-id="1af53-113">Para que un tema se confirme, debe haber una red de dos votos positivos recibidos de usuarios que votaron mediante el mecanismo de comentarios en la tarjeta del tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-113">For a topic to be confirmed, there must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="1af53-114">Por ejemplo, si un usuario votó positivo y un usuario votó negativo para un tema en particular, aún necesitará dos votos positivos más para confirmar el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-114">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="1af53-115">**Publicado:** un tema confirmado que se ha seleccionado: se han realizado ediciones manuales para mejorar su calidad.</span><span class="sxs-lookup"><span data-stu-id="1af53-115">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>

- <span data-ttu-id="1af53-116">**Eliminado:** un administrador de conocimientos rechaza un tema y ya no será visible para los visores.</span><span class="sxs-lookup"><span data-stu-id="1af53-116">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="1af53-117">Un tema se puede quitar en cualquier estado (sugerido, confirmado o publicado).</span><span class="sxs-lookup"><span data-stu-id="1af53-117">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="1af53-118">Para que se quite un tema, debe haber una red de dos votos negativos recibidos de los usuarios que votaron con los mecanismos de comentarios en la tarjeta del tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-118">For a topic to be removed, there must be a net of two negative votes received from users who voted using the feedback mechanisms on the topic card.</span></span> <span data-ttu-id="1af53-119">Por ejemplo, si un usuario votó negativo y un usuario votó positivo para un tema en particular, aún necesitará dos votos negativos más para que se elimine el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-119">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span> <span data-ttu-id="1af53-120">Cuando se quita un tema publicado, la página con los detalles seleccionados tendrá que eliminarse manualmente a través de la Biblioteca de páginas del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="1af53-120">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="1af53-121">En la página Administrar **temas,** cada administrador de conocimientos solo podrá ver temas en los que tengan acceso a los archivos y páginas subyacentes conectados al tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-121">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="1af53-122">Este recorte de permisos se reflejará en la lista de temas que aparecen en las pestañas **Sugerido,** **Confirmado,** Publicado **y** Eliminado.</span><span class="sxs-lookup"><span data-stu-id="1af53-122">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="1af53-123">Sin embargo, los recuentos de temas muestran los recuentos totales de la organización independientemente de los permisos.</span><span class="sxs-lookup"><span data-stu-id="1af53-123">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="1af53-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1af53-124">Requirements</span></span>

<span data-ttu-id="1af53-125">Para administrar temas en el centro de temas, debe:</span><span class="sxs-lookup"><span data-stu-id="1af53-125">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="1af53-126">Tener una licencia de Temas Microsoft Viva.</span><span class="sxs-lookup"><span data-stu-id="1af53-126">Have a Viva Topics license.</span></span>

- <span data-ttu-id="1af53-127">Tenga el [**Quién puede administrar permisos de temas.**](./topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="1af53-127">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="1af53-128">Los administradores del conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema de Temas Viva.</span><span class="sxs-lookup"><span data-stu-id="1af53-128">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="1af53-129">No podrá ver la  página Administrar temas en el centro de temas a menos que tenga el permiso **Quién administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="1af53-129">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="1af53-130">En el centro de temas, un administrador de conocimientos puede revisar los temas que se han identificado en las ubicaciones de origen especificadas y puede confirmarlos o quitarlos.</span><span class="sxs-lookup"><span data-stu-id="1af53-130">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="1af53-131">Un administrador de conocimientos también puede crear y publicar nuevas páginas de temas si no se encontró una en la detección de temas o editar las existentes si es necesario actualizarlas.</span><span class="sxs-lookup"><span data-stu-id="1af53-131">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="1af53-132">Revisar temas sugeridos</span><span class="sxs-lookup"><span data-stu-id="1af53-132">Review suggested topics</span></span>

<span data-ttu-id="1af53-133">En la **página Administrar temas,** los temas que se detectaron en las ubicaciones SharePoint de origen especificadas se mostrarán en la **pestaña Sugerencias.** Si es necesario, un administrador de conocimientos puede revisar temas no confirmados y elegir confirmarlos o quitarlos.</span><span class="sxs-lookup"><span data-stu-id="1af53-133">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Temas sugeridos](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="1af53-135">Para revisar un tema sugerido:</span><span class="sxs-lookup"><span data-stu-id="1af53-135">To review a suggested topic:</span></span>

1. <span data-ttu-id="1af53-136">En la **página Administrar temas,** seleccione la **pestaña Sugerencia** y, a continuación, seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-136">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="1af53-137">En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="1af53-137">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="1af53-138">La publicación de cualquier modificación moverá este tema a la **pestaña Publicado.**</span><span class="sxs-lookup"><span data-stu-id="1af53-138">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="1af53-139">Después de revisar el tema, vuelva a la **página Administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="1af53-139">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="1af53-140">Para el tema seleccionado, puede:</span><span class="sxs-lookup"><span data-stu-id="1af53-140">For the selected topic, you can:</span></span>

   - <span data-ttu-id="1af53-141">Seleccione la marca de verificación para confirmar el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-141">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="1af53-142">Seleccione la **x** si desea quitar el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-142">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="1af53-143">Los temas confirmados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **lista** Confirmados.</span><span class="sxs-lookup"><span data-stu-id="1af53-143">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="1af53-144">Los temas eliminados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **pestaña** Eliminado.</span><span class="sxs-lookup"><span data-stu-id="1af53-144">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="1af53-145">Puntuación de calidad</span><span class="sxs-lookup"><span data-stu-id="1af53-145">Quality score</span></span>

<span data-ttu-id="1af53-146">Cada tema que aparece en la **página Temas** sugeridos tiene asignada una puntuación de calidad.</span><span class="sxs-lookup"><span data-stu-id="1af53-146">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="1af53-147">La puntuación de calidad es un reflejo de la cantidad de información que el usuario promedio verá para la información sobre el tema, teniendo en cuenta que cada usuario puede ver más o menos información debido a los permisos que podrían o no tener en la información de un tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-147">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="1af53-148">La puntuación de calidad puede ayudar a proporcionar información sobre los temas con más información y puede ser útil para encontrar temas que pueden necesitar editarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="1af53-148">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="1af53-149">Por ejemplo, un tema con una puntuación de calidad inferior puede ser el resultado de que algunos usuarios no tengan permisos SharePoint los archivos o sitios pertinentes que AI ha incluido en el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-149">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="1af53-150">A continuación, un colaborador podría editar el tema para incluir la información (cuando corresponda), que, a continuación, se podrá ver para todos los usuarios que puedan ver el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-150">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="1af53-151">Impresiones</span><span class="sxs-lookup"><span data-stu-id="1af53-151">Impressions</span></span>

<span data-ttu-id="1af53-152">La **columna Impresiones** muestra el número de veces que se ha mostrado un tema a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="1af53-152">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="1af53-153">Esto incluye vistas a través de las tarjetas de respuesta del tema en la búsqueda y a través de los aspectos destacados del tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-153">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="1af53-154">No refleja el clic en estos temas, sino que se ha mostrado el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-154">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="1af53-155">La **columna Impresiones se** mostrará para los temas de  las pestañas **Sugeridos,**  **Confirmados,** Publicados y Eliminados de la página Administrar **temas.**</span><span class="sxs-lookup"><span data-stu-id="1af53-155">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="1af53-156">Temas confirmados</span><span class="sxs-lookup"><span data-stu-id="1af53-156">Confirmed topics</span></span>

<span data-ttu-id="1af53-157">En  la página Administrar temas, los temas detectados en las ubicaciones de origen de SharePoint especificadas y confirmados por un administrador de conocimientos o "crowdsourced" confirmados por una  red de dos o más personas (equilibrando los votos negativos del usuario con los votos positivos de los usuarios) a través del mecanismo de comentarios de tarjeta se mostrarán en la pestaña Confirmado. Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="1af53-157">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="1af53-158">Para revisar un tema confirmado:</span><span class="sxs-lookup"><span data-stu-id="1af53-158">To review a confirmed topic:</span></span>

1. <span data-ttu-id="1af53-159">En la **pestaña Confirmado,** seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-159">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="1af53-160">En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="1af53-160">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="1af53-161">Tenga en cuenta que todavía puede optar por rechazar un tema confirmado.</span><span class="sxs-lookup"><span data-stu-id="1af53-161">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="1af53-162">Para ello, vaya al tema seleccionado en la **pestaña** Confirmado y seleccione **la x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="1af53-162">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="1af53-163">Temas publicados</span><span class="sxs-lookup"><span data-stu-id="1af53-163">Published topics</span></span>

<span data-ttu-id="1af53-164">Los temas publicados se han editado para que la información específica siempre aparezca a quien encuentre la página.</span><span class="sxs-lookup"><span data-stu-id="1af53-164">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="1af53-165">Aquí también se enumeran los temas creados manualmente.</span><span class="sxs-lookup"><span data-stu-id="1af53-165">Manually created topics are listed here as well.</span></span>

   ![Administrar temas](../media/knowledge-management/manage-topics-new.png)
