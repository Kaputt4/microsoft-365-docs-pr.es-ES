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
ms.openlocfilehash: f2429b0ffdd4a238bc9322ae9199eebbbfd407b5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651167"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="c2d52-103">Administrar temas en el centro de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="c2d52-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="c2d52-104">En el Centro de temas de Viva  Topics, un administrador de conocimientos puede ver la página Administrar temas para revisar los temas que se han identificado en las ubicaciones de origen según lo especificado por el administrador de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="c2d52-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Centro de temas](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="c2d52-106">Fases del tema</span><span class="sxs-lookup"><span data-stu-id="c2d52-106">Topic stages</span></span>

<span data-ttu-id="c2d52-107">Los administradores de conocimientos ayudan a guiar los temas detectados a través de las distintas fases del ciclo de vida del tema: **Sugerido** **,** **Confirmado**, Publicado y **Eliminado.**</span><span class="sxs-lookup"><span data-stu-id="c2d52-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Gráfico de ciclo de vida de temas](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="c2d52-109">**Sugerido**: se ha identificado un tema en AI y tiene suficientes recursos compatibles, conexiones y propiedades.</span><span class="sxs-lookup"><span data-stu-id="c2d52-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="c2d52-110">(Se marcan como **un tema sugerido** en la interfaz de usuario).</span><span class="sxs-lookup"><span data-stu-id="c2d52-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="c2d52-111">**Confirmado:** un tema que ha sido detectado por AI y que se ha validado.</span><span class="sxs-lookup"><span data-stu-id="c2d52-111">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="c2d52-112">La validación del tema se produce cuando:</span><span class="sxs-lookup"><span data-stu-id="c2d52-112">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="c2d52-113">Un administrador de conocimientos confirma un tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-113">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="c2d52-114">Un administrador de [conocimientos confirma un tema en](manage-topics.md#confirmed-topics) la página Administrar **temas.**</span><span class="sxs-lookup"><span data-stu-id="c2d52-114">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="c2d52-115">Varios usuarios confirman un tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-115">Multiple users confirm a topic.</span></span> <span data-ttu-id="c2d52-116">Debe haber una red de dos votos positivos recibidos de usuarios que votaron mediante el mecanismo de comentarios en la tarjeta de tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-116">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="c2d52-117">Por ejemplo, si un usuario votó positivo y un usuario votó negativo para un tema en particular, aún necesitará dos votos positivos más para confirmar el tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-117">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="c2d52-118">**Publicado:** tema que se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c2d52-118">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="c2d52-119">Se han realizado modificaciones manuales para mejorar su calidad o ha sido creada por un usuario.</span><span class="sxs-lookup"><span data-stu-id="c2d52-119">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="c2d52-120">**Eliminado:** un tema que se ha rechazado y que ya no será visible para los visores.</span><span class="sxs-lookup"><span data-stu-id="c2d52-120">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="c2d52-121">Un tema se puede quitar en cualquier estado (sugerido, confirmado o publicado).</span><span class="sxs-lookup"><span data-stu-id="c2d52-121">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="c2d52-122">La eliminación del tema se produce cuando:</span><span class="sxs-lookup"><span data-stu-id="c2d52-122">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="c2d52-123">Un administrador de conocimientos quita un tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-123">A knowledge manager removes a topic.</span></span> <span data-ttu-id="c2d52-124">Un administrador de conocimientos quita un tema de la **página Administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="c2d52-124">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="c2d52-125">Varios usuarios emitirán votos negativos mediante el mecanismo de comentarios en la tarjeta de tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-125">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="c2d52-126">Para que se quite un tema, debe haber una red de dos votos negativos recibidos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c2d52-126">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="c2d52-127">Por ejemplo, si un usuario votó negativo y un usuario votó positivo para un tema en particular, aún necesitará dos votos negativos más para que se elimine el tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-127">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="c2d52-128">Cuando se quita un tema publicado, la página con los detalles seleccionados tendrá que eliminarse manualmente a través de la Biblioteca de páginas del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="c2d52-128">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="c2d52-129">En la página Administrar **temas,** cada administrador de conocimientos solo podrá ver temas en los que tengan acceso a los archivos y páginas subyacentes conectados al tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-129">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="c2d52-130">Este recorte de permisos se reflejará en la lista de temas que aparecen en las pestañas **Sugerido,** **Confirmado,** Publicado **y** Eliminado.</span><span class="sxs-lookup"><span data-stu-id="c2d52-130">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="c2d52-131">Sin embargo, los recuentos de temas muestran los recuentos totales de la organización independientemente de los permisos.</span><span class="sxs-lookup"><span data-stu-id="c2d52-131">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="c2d52-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2d52-132">Requirements</span></span>

<span data-ttu-id="c2d52-133">Para administrar temas en el centro de temas, debe:</span><span class="sxs-lookup"><span data-stu-id="c2d52-133">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="c2d52-134">Tener una licencia de Temas Microsoft Viva.</span><span class="sxs-lookup"><span data-stu-id="c2d52-134">Have a Viva Topics license.</span></span>

- <span data-ttu-id="c2d52-135">Tenga el [**Quién puede administrar permisos de temas.**](./topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="c2d52-135">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="c2d52-136">Los Administradores de conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema de Temas Viva.</span><span class="sxs-lookup"><span data-stu-id="c2d52-136">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="c2d52-137">No podrá ver la  página Administrar temas en el centro de temas a menos que tenga el permiso **Quién administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="c2d52-137">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="c2d52-138">En el centro de temas, un administrador de conocimientos puede revisar los temas que se han identificado en las ubicaciones de origen especificadas y puede confirmarlos o quitarlos.</span><span class="sxs-lookup"><span data-stu-id="c2d52-138">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="c2d52-139">Un administrador de conocimientos también puede crear y publicar nuevas páginas de temas si no se encontró una en la detección de temas o editar las existentes si es necesario actualizarlas.</span><span class="sxs-lookup"><span data-stu-id="c2d52-139">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="c2d52-140">Revisar temas sugeridos</span><span class="sxs-lookup"><span data-stu-id="c2d52-140">Review suggested topics</span></span>

<span data-ttu-id="c2d52-141">En la **página Administrar temas,** los temas que se detectaron en las ubicaciones SharePoint de origen especificadas se mostrarán en la **pestaña Sugerencias.** Si es necesario, un administrador de conocimientos puede revisar temas no confirmados y elegir confirmarlos o quitarlos.</span><span class="sxs-lookup"><span data-stu-id="c2d52-141">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Temas sugeridos](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="c2d52-143">Para revisar un tema sugerido:</span><span class="sxs-lookup"><span data-stu-id="c2d52-143">To review a suggested topic:</span></span>

1. <span data-ttu-id="c2d52-144">En la **página Administrar temas,** seleccione la **pestaña Sugerencia** y, a continuación, seleccione el tema para abrir la página del tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-144">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="c2d52-145">En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="c2d52-145">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="c2d52-146">La publicación de cualquier modificación moverá este tema a la **pestaña Publicado.**</span><span class="sxs-lookup"><span data-stu-id="c2d52-146">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="c2d52-147">Después de revisar el tema, vuelva a la **página Administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="c2d52-147">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="c2d52-148">Para el tema seleccionado, puede:</span><span class="sxs-lookup"><span data-stu-id="c2d52-148">For the selected topic, you can:</span></span>

   - <span data-ttu-id="c2d52-149">Seleccionar la marca de verificación para confirmar el tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-149">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="c2d52-150">Seleccione la **x** si desea quitar el tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-150">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="c2d52-151">Los temas confirmados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **lista** Confirmados.</span><span class="sxs-lookup"><span data-stu-id="c2d52-151">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="c2d52-152">Los temas eliminados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **pestaña** Eliminado.</span><span class="sxs-lookup"><span data-stu-id="c2d52-152">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="c2d52-153">Puntuación de calidad</span><span class="sxs-lookup"><span data-stu-id="c2d52-153">Quality score</span></span>

<span data-ttu-id="c2d52-154">Cada tema que aparece en la **página Temas** sugeridos tiene asignada una puntuación de calidad.</span><span class="sxs-lookup"><span data-stu-id="c2d52-154">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="c2d52-155">La puntuación de calidad es un reflejo de la cantidad de información que el usuario promedio verá para la información sobre el tema, teniendo en cuenta que cada usuario puede ver más o menos información debido a los permisos que podrían o no tener en la información de un tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-155">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="c2d52-156">La puntuación de calidad puede ayudar a proporcionar información sobre los temas con más información y puede ser útil para encontrar temas que pueden necesitar editarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="c2d52-156">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="c2d52-157">Por ejemplo, un tema con una puntuación de calidad inferior puede ser el resultado de que algunos usuarios no tengan permisos SharePoint los archivos o sitios pertinentes que AI ha incluido en el tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-157">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="c2d52-158">A continuación, un colaborador podría editar el tema para incluir la información (cuando sea necesaria), lo que estará visible para todos los usuarios que puedan verlo.</span><span class="sxs-lookup"><span data-stu-id="c2d52-158">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="c2d52-159">Impresiones</span><span class="sxs-lookup"><span data-stu-id="c2d52-159">Impressions</span></span>

<span data-ttu-id="c2d52-160">La **columna Impresiones** muestra el número de veces que se ha mostrado un tema a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="c2d52-160">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="c2d52-161">Esto incluye vistas a través de las tarjetas de respuesta del tema en la búsqueda y a través de los aspectos destacados del tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-161">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="c2d52-162">No refleja el clic en estos temas, sino que se ha mostrado el tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-162">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="c2d52-163">La **columna Impresiones se** mostrará para los temas de  las pestañas **Sugeridos,**  **Confirmados,** Publicados y Eliminados de la página Administrar **temas.**</span><span class="sxs-lookup"><span data-stu-id="c2d52-163">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="c2d52-164">Temas confirmados</span><span class="sxs-lookup"><span data-stu-id="c2d52-164">Confirmed topics</span></span>

<span data-ttu-id="c2d52-165">En  la página Administrar temas, los temas detectados en las ubicaciones de origen de SharePoint especificadas y confirmados por un administrador de conocimientos o "crowdsourced" confirmados por una  red de dos o más personas (equilibrando los votos negativos del usuario con los votos positivos de los usuarios) a través del mecanismo de comentarios de tarjeta se mostrarán en la pestaña Confirmado. Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.</span><span class="sxs-lookup"><span data-stu-id="c2d52-165">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="c2d52-166">Para revisar un tema confirmado:</span><span class="sxs-lookup"><span data-stu-id="c2d52-166">To review a confirmed topic:</span></span>

1. <span data-ttu-id="c2d52-167">En la pestaña **Confirmado**, seleccione el tema para abrir la página de tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-167">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="c2d52-168">En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.</span><span class="sxs-lookup"><span data-stu-id="c2d52-168">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="c2d52-169">Tenga en cuenta que todavía puede optar por rechazar un tema confirmado.</span><span class="sxs-lookup"><span data-stu-id="c2d52-169">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="c2d52-170">Para ello, vaya al tema seleccionado en la **pestaña** Confirmado y seleccione **la x** si desea rechazar el tema.</span><span class="sxs-lookup"><span data-stu-id="c2d52-170">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="c2d52-171">Temas publicados</span><span class="sxs-lookup"><span data-stu-id="c2d52-171">Published topics</span></span>

<span data-ttu-id="c2d52-172">Los temas publicados se han editado para que la información específica siempre aparezca a quien encuentre la página.</span><span class="sxs-lookup"><span data-stu-id="c2d52-172">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="c2d52-173">Aquí también se muestran los temas creados manualmente.</span><span class="sxs-lookup"><span data-stu-id="c2d52-173">Manually created topics are listed here as well.</span></span>

   ![Administrar temas](../media/knowledge-management/manage-topics-new.png)

## <a name="topic-count-dashboard"></a><span data-ttu-id="c2d52-175">Panel de recuento de temas</span><span class="sxs-lookup"><span data-stu-id="c2d52-175">Topic count dashboard</span></span>

<span data-ttu-id="c2d52-176">Este gráfico de la vista panel le permite ver el número de temas en el Centro de temas de Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="c2d52-176">This chart in the dashboard view lets you see the number of topics in your Viva Topics topic center.</span></span> <span data-ttu-id="c2d52-177">El gráfico muestra los recuentos de temas por fase de ciclo de vida del tema y también muestra cómo los recuentos de temas han tenido tendencia con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="c2d52-177">The chart shows the topic counts per topic lifecycle stage and also shows how topic counts have trended over time.</span></span> <span data-ttu-id="c2d52-178">Los administradores de conocimientos pueden supervisar visualmente la velocidad a la que AI detecta nuevos temas y la velocidad a la que el administrador de conocimientos o las acciones del usuario confirman o publican los temas.</span><span class="sxs-lookup"><span data-stu-id="c2d52-178">Knowledge managers can visually monitor the rate at which new topics are being discovered by AI and the rate at which topics are getting confirmed or published by the knowledge manager or user actions.</span></span>

<span data-ttu-id="c2d52-179">Los administradores de conocimientos pueden ver un número  diferente de temas representados en la lista de temas de la página Administrar temas de los que se ven en el panel.</span><span class="sxs-lookup"><span data-stu-id="c2d52-179">Knowledge managers might see a different count of topics represented in the list of topics on the **Manage topics** page than they see in the dashboard.</span></span> <span data-ttu-id="c2d52-180">Esto se debe a que es posible que un administrador de conocimientos no tenga acceso a todos los temas.</span><span class="sxs-lookup"><span data-stu-id="c2d52-180">This is because a knowledge manager might not have access to all topics.</span></span> <span data-ttu-id="c2d52-181">El recuento que se muestra en la vista de panel se toma antes de aplicar el recorte de permisos.</span><span class="sxs-lookup"><span data-stu-id="c2d52-181">The count presented in the dashboard view is taken before applying permission-trimming.</span></span> 

   ![Captura de pantalla del panel de recuento de temas](../media/knowledge-management/topic-count-dashboard.png)
