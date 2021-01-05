---
title: Configurar experiencias de tema en Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo configurar experiencias de tema en Microsoft 365
ms.openlocfilehash: d221f2932dc2ca9f562800b7b274e35e7f3d1db3
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749616"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="2cc43-103">Configurar experiencias de tema en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc43-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="2cc43-104">Puede usar el centro de administración de Microsoft 365 para instalar y configurar las experiencias de los [temas](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2cc43-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="2cc43-105">Es importante planear la mejor forma de configurar y configurar temas en el entorno.</span><span class="sxs-lookup"><span data-stu-id="2cc43-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="2cc43-106">Asegúrese de leer las [experiencias del tema del plan](plan-topic-experiences.md) antes de comenzar con los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="2cc43-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="2cc43-107">Debe ser administrador global o administrador de SharePoint para tener acceso al centro de administración de Microsoft 365 y configurar las experiencias de los temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="2cc43-108">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="2cc43-108">Video demonstration</span></span>

<span data-ttu-id="2cc43-109">En este vídeo se muestra el proceso de configuración de experiencias de tema en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cc43-109">This video shows the process for setting up topic experiences in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="2cc43-110">Configurar las experiencias temáticas</span><span class="sxs-lookup"><span data-stu-id="2cc43-110">Set up topic experiences</span></span>

<span data-ttu-id="2cc43-111">Para configurar experiencias de tema en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc43-111">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="2cc43-112">En el [centro de administración de Microsoft 365](https://admin.microsoft.com), seleccione **instalación** y, a continuación, ver la sección **archivos y contenido** .</span><span class="sxs-lookup"><span data-stu-id="2cc43-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="2cc43-113">En la sección **archivos y contenido** , haga clic en **conectar personas con el conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Conectar a personas con el conocimiento](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="2cc43-115">En la página **conectar personas a los conocimientos** , **haga clic en introducción para** guiarlo en el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="2cc43-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Introducción](../media/k-get-started.png) 

4. <span data-ttu-id="2cc43-117">En la página **elegir el modo en que la red de conocimiento puede buscar temas** , se configurará la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-117">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="2cc43-118">En la sección **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="2cc43-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="2cc43-119">Elija entre:</span><span class="sxs-lookup"><span data-stu-id="2cc43-119">Choose from:</span></span>
    - <span data-ttu-id="2cc43-120">**Todos los sitios**: todos los sitios de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="2cc43-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="2cc43-121">Esto incluye los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="2cc43-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="2cc43-122">**Todos, excepto los sitios seleccionados**: escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="2cc43-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="2cc43-123">También puede cargar una lista de sitios que desea excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="2cc43-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="2cc43-124">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="2cc43-125">**Solo sitios seleccionados**: escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="2cc43-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="2cc43-126">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="2cc43-126">You can also upload a list of sites.</span></span> <span data-ttu-id="2cc43-127">Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="2cc43-128">**Sin sitios**: no incluye ningún sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cc43-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Elegir cómo buscar temas](../media/ksetup1.png) 
   
5. <span data-ttu-id="2cc43-130">En la sección **excluir temas por nombre** , puede Agregar nombres de temas que desea excluir del descubrimiento de temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="2cc43-131">Use esta configuración para evitar que la información confidencial se incluya como temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="2cc43-132">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="2cc43-132">The options are:</span></span>
    - <span data-ttu-id="2cc43-133">**No excluir temas**</span><span class="sxs-lookup"><span data-stu-id="2cc43-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="2cc43-134">**Excluir temas por nombre**</span><span class="sxs-lookup"><span data-stu-id="2cc43-134">**Exclude topics by name**</span></span>

    ![Excluir temas](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="2cc43-136">(Los administradores de conocimiento también pueden excluir temas del centro de temas después de la detección).</span><span class="sxs-lookup"><span data-stu-id="2cc43-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="2cc43-137">Cómo excluir temas por nombre</span><span class="sxs-lookup"><span data-stu-id="2cc43-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="2cc43-138">Si necesita excluir temas, después de seleccionar **excluir temas por nombre**, seleccione Descargar la plantilla. csv y actualizarla con la lista de temas que desea excluir de los resultados de la detección.</span><span class="sxs-lookup"><span data-stu-id="2cc43-138">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir temas en la plantilla CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="2cc43-140">En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:</span><span class="sxs-lookup"><span data-stu-id="2cc43-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="2cc43-141">**Name**: escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="2cc43-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="2cc43-142">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="2cc43-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="2cc43-143">Coincidencia exacta: puede incluir el acrónimo o el nombre exacto (por ejemplo, *contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="2cc43-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="2cc43-144">Coincidencia parcial: puede excluir todos los temas que contengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="2cc43-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="2cc43-145">Por ejemplo, *arco* excluirá todos los temas que contengan la palabra *Arc* , como *círculo arco*, *soldadura de arco de plasma* o arco de *formación*. Tenga en cuenta que no se excluirán los temas en los que se incluya el texto como parte de una palabra, como la *arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="2cc43-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="2cc43-146">**Significa (opcional)**: Si desea excluir un acrónimo, escriba las palabras que representa el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="2cc43-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="2cc43-147">**MatchType-Exact/Partial**: escriba si el nombre que ha escrito es un tipo de coincidencia *exacta* o *parcial* .</span><span class="sxs-lookup"><span data-stu-id="2cc43-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="2cc43-148">Después de completar y guardar el archivo. csv, seleccione **examinar** para buscarlo y seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="2cc43-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="2cc43-149">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-149">Select **Next**.</span></span>

6. <span data-ttu-id="2cc43-150">En la página **quién puede ver los temas y dónde puede** verlos, configurará la visibilidad de los temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="2cc43-151">En los **temas quién puede ver en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-151">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="2cc43-152">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="2cc43-152">You can select:</span></span>
    - <span data-ttu-id="2cc43-153">**Todos los usuarios de mi organización**</span><span class="sxs-lookup"><span data-stu-id="2cc43-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="2cc43-154">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2cc43-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="2cc43-155">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="2cc43-155">**No one**</span></span>

    ![Quién puede ver los temas](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="2cc43-157">Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de temas que tengan asignada una licencia podrán ver los temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="2cc43-158">En la página **permisos para la administración de temas** , elija quién podrá crear, editar o administrar temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="2cc43-159">En la sección **quién puede crear y editar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="2cc43-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="2cc43-160">**Todos los usuarios de mi organización**</span><span class="sxs-lookup"><span data-stu-id="2cc43-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="2cc43-161">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2cc43-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="2cc43-162">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="2cc43-162">**No one**</span></span>

    ![Permisos para la administración de temas, que pueden crear y editar temas](../media/ksetup3.png) 

8. <span data-ttu-id="2cc43-164">En la sección **quién puede administrar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="2cc43-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="2cc43-165">**Todos los usuarios de mi organización**</span><span class="sxs-lookup"><span data-stu-id="2cc43-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="2cc43-166">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2cc43-166">**Only selected people or security groups**</span></span>

    ![Permisos para la administración de temas](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="2cc43-168">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-168">Select **Next**.</span></span>

9. <span data-ttu-id="2cc43-169">En la página **crear centro de temas** , puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y administrar los temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="2cc43-170">En el cuadro **nombre del sitio** , escriba un nombre para el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-170">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="2cc43-171">Opcionalmente, puede escribir una descripción breve en el cuadro **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="2cc43-171">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="2cc43-172">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-172">Select **Next**.</span></span>

   ![Crear centro de conocimiento](../media/ksetup4.png)  

10. <span data-ttu-id="2cc43-174">En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="2cc43-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2cc43-175">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="2cc43-176">Se mostrará la página de **información de red activada** , confirmando que el sistema empezará a analizar los sitios seleccionados para ver los temas y crear el sitio del centro de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="2cc43-176">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="2cc43-177">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-177">Select **Done**.</span></span>

12. <span data-ttu-id="2cc43-178">Se le devolverá a la página **conectar personas a la información** .</span><span class="sxs-lookup"><span data-stu-id="2cc43-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="2cc43-179">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="2cc43-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configuración aplicada](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="2cc43-181">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="2cc43-181">Assign licenses</span></span>

<span data-ttu-id="2cc43-182">Una vez que haya configurado las experiencias de los temas, debe asignar licencias para los usuarios que vayan a usar las experiencias de los temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-182">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="2cc43-183">Solo los usuarios con una licencia pueden ver información sobre temas como las sugerencias, las tarjetas de temas, las páginas de temas y el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="2cc43-184">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="2cc43-184">To assign licenses:</span></span>

1. <span data-ttu-id="2cc43-185">En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="2cc43-186">Seleccione los usuarios a los que desea conceder licencias y haga clic en **Administrar licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-186">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="2cc43-187">Seleccione **Asignar más**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-187">Select **Assign more**.</span></span>

4. <span data-ttu-id="2cc43-188">En **licencias**, seleccione **experiencias del tema**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-188">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="2cc43-189">En **aplicaciones**, asegúrese de que la **búsqueda de conectores de gráficos con** experiencias de índice y **tema** estén seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="2cc43-189">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2cc43-190">![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="2cc43-190">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="2cc43-191">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="2cc43-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="2cc43-192">Administrar experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="2cc43-192">Manage topic experiences</span></span>

<span data-ttu-id="2cc43-193">Una vez que haya configurado las experiencias de los temas, puede cambiar la configuración que eligió durante la instalación en el [centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="2cc43-193">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="2cc43-194">Consulte las siguientes referencias:</span><span class="sxs-lookup"><span data-stu-id="2cc43-194">See the following references:</span></span>

- [<span data-ttu-id="2cc43-195">Administrar la detección de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc43-195">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="2cc43-196">Administrar la visibilidad de los temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc43-196">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="2cc43-197">Administrar los permisos de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc43-197">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="2cc43-198">Cambiar el nombre del centro de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc43-198">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="2cc43-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2cc43-199">See also</span></span>

[<span data-ttu-id="2cc43-200">Información general sobre las experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="2cc43-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
