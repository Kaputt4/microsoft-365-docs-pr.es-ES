---
title: 'Administración de la red de administración de conocimientos (vista previa) '
description: Cómo configurar la administración del conocimiento.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: af53f4d563d286ad29138f935fbb69aa10b902ca
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612625"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="55af6-103">Administración de la red de administración de conocimientos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="55af6-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="55af6-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="55af6-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="55af6-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="55af6-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="55af6-106">Después de [configurar la administración de conocimiento](set-up-knowledge-network.md), en cualquier momento, un administrador puede realizar ajustes en los valores de configuración a través del centro de administración 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55af6-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="55af6-107">Por ejemplo, es posible que deba ajustar la configuración para cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="55af6-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="55af6-108">Agregar nuevos orígenes de SharePoint a los temas de mío.</span><span class="sxs-lookup"><span data-stu-id="55af6-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="55af6-109">Cambiar los usuarios que tendrán acceso a los temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="55af6-110">Cambiar los usuarios que tienen permisos para realizar tareas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="55af6-111">Cambiar el nombre del centro de temas</span><span class="sxs-lookup"><span data-stu-id="55af6-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="55af6-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="55af6-112">Requirements</span></span> 
<span data-ttu-id="55af6-113">Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y administrar las tareas de conocimiento de la organización.</span><span class="sxs-lookup"><span data-stu-id="55af6-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="55af6-114">Para obtener acceso a la configuración de administración de conocimiento:</span><span class="sxs-lookup"><span data-stu-id="55af6-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="55af6-115">En el centro de administración de Microsoft 365, seleccione **instalación**y, a continuación, ver la sección de conocimientos de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="55af6-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="55af6-116">En la sección conocimientos de la **organización** , haga clic en **conectar personas con el conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="55af6-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Conectar a personas con el conocimiento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="55af6-118">En la página **conectar personas a los conocimientos** , seleccione **administrar** para abrir el panel Configuración de la red de **conocimientos** .</span><span class="sxs-lookup"><span data-stu-id="55af6-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![información: configuración de la red](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="55af6-120">Cambiar el modo en que la red de conocimiento puede encontrar temas</span><span class="sxs-lookup"><span data-stu-id="55af6-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="55af6-121">Seleccione la pestaña **detección de temas** si desea actualizar las opciones para los orígenes de temas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="55af6-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="55af6-122">Esta opción le permite seleccionar los sitios de SharePoint de su inquilino que se rastrearán y expondrán para temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="55af6-123">En la pestaña **detección de temas** , en **seleccionar orígenes de temas de SharePoint**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="55af6-124">En la página **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="55af6-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="55af6-125">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="55af6-125">This includes:</span></span></br>
    <span data-ttu-id="55af6-126">a.</span><span class="sxs-lookup"><span data-stu-id="55af6-126">a.</span></span> <span data-ttu-id="55af6-127">**Todos los sitios**: todos los sitios de SharePoint de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="55af6-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="55af6-128">Esto captura los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="55af6-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="55af6-129">b.</span><span class="sxs-lookup"><span data-stu-id="55af6-129">b.</span></span> <span data-ttu-id="55af6-130">**Todos, excepto los sitios seleccionados**: escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="55af6-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="55af6-131">También puede cargar una lista de sitios que desea excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="55af6-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="55af6-132">Los sitios que se creen en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="55af6-133">c.</span><span class="sxs-lookup"><span data-stu-id="55af6-133">c.</span></span> <span data-ttu-id="55af6-134">**Solo sitios seleccionados**: escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="55af6-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="55af6-135">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="55af6-135">You can also upload a list of sites.</span></span> <span data-ttu-id="55af6-136">Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Elegir cómo buscar temas](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="55af6-138">Si tiene un número de sitios que desea excluir (si selecciona **todos, excepto los sitios seleccionados**) o incluir (si seleccionó **solo sitios seleccionados**), puede elegir cargar un archivo CSV con los nombres de sitio y las direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="55af6-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="55af6-139">Puede descargar la **plantilla del sitio download. csv** si desea usar el archivo de plantilla CSV.</span><span class="sxs-lookup"><span data-stu-id="55af6-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="55af6-140">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="55af6-141">Cambiar quién puede ver los temas de la organización</span><span class="sxs-lookup"><span data-stu-id="55af6-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="55af6-142">Seleccione la pestaña **detección de temas** si desea actualizar quién en su organización puede ver temas descubiertos en los resultados de la búsqueda y cuándo los temas están resaltados en contenido, como las páginas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="55af6-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="55af6-143">En la pestaña **detección de temas** , en **quién puede ver los temas de la red de conocimiento**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="55af6-144">En la página **quién puede ver los temas en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="55af6-145">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="55af6-145">You can select:</span></span></br>
    <span data-ttu-id="55af6-146">a.</span><span class="sxs-lookup"><span data-stu-id="55af6-146">a.</span></span> <span data-ttu-id="55af6-147">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="55af6-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="55af6-148">b.</span><span class="sxs-lookup"><span data-stu-id="55af6-148">b.</span></span> <span data-ttu-id="55af6-149">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="55af6-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="55af6-150">c.</span><span class="sxs-lookup"><span data-stu-id="55af6-150">c.</span></span> <span data-ttu-id="55af6-151">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="55af6-151">**No one**</span></span></br>

    ![Quién puede ver los temas](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="55af6-153">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="55af6-154">Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de administración de conocimiento podrán ver los temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="55af6-155">Cambiar quién tiene permisos para realizar tareas en el centro de temas</span><span class="sxs-lookup"><span data-stu-id="55af6-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="55af6-156">Seleccione la pestaña **permisos de temas** si desea actualizar quién tiene permisos para hacer lo siguiente en la página centro de temas:</span><span class="sxs-lookup"><span data-stu-id="55af6-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="55af6-157">Qué usuarios pueden crear y editar temas: crear temas nuevos que no se encontraron durante la detección o editar los detalles de la página del tema existente.</span><span class="sxs-lookup"><span data-stu-id="55af6-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="55af6-158">Qué usuarios pueden administrar temas: confirmar o rechazar temas descubiertos.</span><span class="sxs-lookup"><span data-stu-id="55af6-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="55af6-159">Para actualizar quién tiene permisos para crear y editar temas:</span><span class="sxs-lookup"><span data-stu-id="55af6-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="55af6-160">En la ficha **permisos de tema** , en **quién puede crear y editar temas**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="55af6-161">En la página **quién puede crear y editar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="55af6-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="55af6-162">a.</span><span class="sxs-lookup"><span data-stu-id="55af6-162">a.</span></span> <span data-ttu-id="55af6-163">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="55af6-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="55af6-164">b.</span><span class="sxs-lookup"><span data-stu-id="55af6-164">b.</span></span> <span data-ttu-id="55af6-165">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="55af6-165">**Only selected people or security groups**</span></span></br>

    ![Creación y edición de temas](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="55af6-167">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-167">Select **Save**.</span></span></br>

<span data-ttu-id="55af6-168">Para actualizar quién tiene permisos para administrar temas:</span><span class="sxs-lookup"><span data-stu-id="55af6-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="55af6-169">En la ficha **permisos de tema** , en **¿quién puede administrar temas**?, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="55af6-170">En la página **quién puede administrar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="55af6-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="55af6-171">a.</span><span class="sxs-lookup"><span data-stu-id="55af6-171">a.</span></span> <span data-ttu-id="55af6-172">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="55af6-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="55af6-173">b.</span><span class="sxs-lookup"><span data-stu-id="55af6-173">b.</span></span> <span data-ttu-id="55af6-174">**Personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="55af6-174">**Selected people or security groups**</span></span></br>

    ![Administrar temas](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="55af6-176">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="55af6-177">Actualizar el nombre del centro de temas</span><span class="sxs-lookup"><span data-stu-id="55af6-177">Update your topic center name</span></span>

<span data-ttu-id="55af6-178">Seleccione la pestaña **centro de temas** si desea actualizar el nombre del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="55af6-179">En la pestaña **centro de temas** , en nombre del centro de **temas**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="55af6-180">En la página **Editar nombre del centro de temas** , en el cuadro Nombre del centro de **temas** , escriba el nuevo nombre del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="55af6-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="55af6-181">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55af6-181">Select **Save**</span></span>

    ![Editar nombre del centro de temas](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="55af6-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55af6-183">See also</span></span>



  






