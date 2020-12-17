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
ms.openlocfilehash: e11f0b75556a4a8ac0ffa40269d7166258128daf
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698560"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="3d338-103">Configurar experiencias de tema en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d338-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="3d338-104">Puede usar el centro de administración de Microsoft 365 para instalar y configurar las experiencias de los [temas](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3d338-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="3d338-105">Es importante planear la mejor forma de configurar y configurar temas en el entorno.</span><span class="sxs-lookup"><span data-stu-id="3d338-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="3d338-106">Asegúrese de leer las [experiencias del tema del plan](plan-topic-experiences.md) antes de comenzar con los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3d338-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="3d338-107">Debe ser administrador global o administrador de SharePoint para tener acceso al centro de administración de Microsoft 365 y configurar las experiencias de los temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="3d338-108">Configurar experiencias de tema</span><span class="sxs-lookup"><span data-stu-id="3d338-108">Set up topic experiences</span></span>

<span data-ttu-id="3d338-109">Para configurar experiencias de tema en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d338-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="3d338-110">En el [centro de administración de Microsoft 365](https://admin.microsoft.com), seleccione **instalación** y, a continuación, ver la sección **archivos y contenido** .</span><span class="sxs-lookup"><span data-stu-id="3d338-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="3d338-111">En la sección **archivos y contenido** , haga clic en **conectar personas con el conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="3d338-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Conectar a personas con el conocimiento](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="3d338-113">En la página **conectar personas a los conocimientos** , **haga clic en introducción para** guiarlo en el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="3d338-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Introducción](../media/k-get-started.png) 

4. <span data-ttu-id="3d338-115">En la página **elegir el modo en que la red de conocimiento puede buscar temas** , se configurará la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="3d338-116">En la sección **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="3d338-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="3d338-117">Elija entre:</span><span class="sxs-lookup"><span data-stu-id="3d338-117">Choose from:</span></span>
    - <span data-ttu-id="3d338-118">**Todos los sitios**: todos los sitios de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="3d338-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="3d338-119">Esto incluye los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="3d338-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="3d338-120">**Todos, excepto los sitios seleccionados**: escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="3d338-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="3d338-121">También puede cargar una lista de sitios que desea excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="3d338-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="3d338-122">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="3d338-123">**Solo sitios seleccionados**: escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="3d338-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="3d338-124">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="3d338-124">You can also upload a list of sites.</span></span> <span data-ttu-id="3d338-125">Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="3d338-126">**Sin sitios**: no incluye ningún sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d338-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Elegir cómo buscar temas](../media/ksetup1.png) 
   
5. <span data-ttu-id="3d338-128">En la sección **excluir temas por nombre** , puede Agregar nombres de temas que desea excluir del descubrimiento de temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="3d338-129">Use esta configuración para evitar que la información confidencial se incluya como temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="3d338-130">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="3d338-130">The options are:</span></span>
    - <span data-ttu-id="3d338-131">**No excluir temas**</span><span class="sxs-lookup"><span data-stu-id="3d338-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="3d338-132">**Excluir temas por nombre**</span><span class="sxs-lookup"><span data-stu-id="3d338-132">**Exclude topics by name**</span></span>

    ![Excluir temas](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="3d338-134">(Los administradores de conocimiento también pueden excluir temas del centro de temas después de la detección).</span><span class="sxs-lookup"><span data-stu-id="3d338-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="3d338-135">Cómo excluir temas por nombre</span><span class="sxs-lookup"><span data-stu-id="3d338-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="3d338-136">Si necesita excluir temas, después de seleccionar **excluir temas por nombre**, seleccione Descargar la plantilla. csv y actualizarla con la lista de temas que desea excluir de los resultados de la detección.</span><span class="sxs-lookup"><span data-stu-id="3d338-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir temas en la plantilla CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="3d338-138">En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:</span><span class="sxs-lookup"><span data-stu-id="3d338-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="3d338-139">**Name**: escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="3d338-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="3d338-140">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="3d338-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="3d338-141">Coincidencia exacta: puede incluir el acrónimo o el nombre exacto (por ejemplo, *contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="3d338-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="3d338-142">Coincidencia parcial: puede excluir todos los temas que contengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="3d338-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="3d338-143">Por ejemplo, *arco* excluirá todos los temas que contengan la palabra *Arc* , como *círculo arco*, *soldadura de arco de plasma* o arco de *formación*. Tenga en cuenta que no se excluirán los temas en los que se incluya el texto como parte de una palabra, como la *arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="3d338-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="3d338-144">**Significa (opcional)**: Si desea excluir un acrónimo, escriba las palabras que representa el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="3d338-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="3d338-145">**MatchType-Exact/Partial**: escriba si el nombre que ha escrito es un tipo de coincidencia *exacta* o *parcial* .</span><span class="sxs-lookup"><span data-stu-id="3d338-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="3d338-146">Después de completar y guardar el archivo. csv, seleccione **examinar** para buscarlo y seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="3d338-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="3d338-147">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3d338-147">Select **Next**.</span></span>

6. <span data-ttu-id="3d338-148">En la página **quién puede ver los temas y dónde puede** verlos, configurará la visibilidad de los temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="3d338-149">En los **temas quién puede ver en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="3d338-150">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="3d338-150">You can select:</span></span>
    - <span data-ttu-id="3d338-151">**Todos los usuarios de mi organización**</span><span class="sxs-lookup"><span data-stu-id="3d338-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="3d338-152">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="3d338-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="3d338-153">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="3d338-153">**No one**</span></span>

    ![Quién puede ver los temas](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="3d338-155">Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de temas que tengan asignada una licencia podrán ver los temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="3d338-156">En la página **permisos para la administración de temas** , elija quién podrá crear, editar o administrar temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="3d338-157">En la sección **quién puede crear y editar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="3d338-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="3d338-158">**Todos los usuarios de mi organización**</span><span class="sxs-lookup"><span data-stu-id="3d338-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="3d338-159">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="3d338-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="3d338-160">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="3d338-160">**No one**</span></span>

    ![Permisos para la administración de temas, que pueden crear y editar temas](../media/ksetup3.png) 

8. <span data-ttu-id="3d338-162">En la sección **quién puede administrar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="3d338-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="3d338-163">**Todos los usuarios de mi organización**</span><span class="sxs-lookup"><span data-stu-id="3d338-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="3d338-164">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="3d338-164">**Only selected people or security groups**</span></span>

    ![Permisos para la administración de temas](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="3d338-166">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3d338-166">Select **Next**.</span></span>

9. <span data-ttu-id="3d338-167">En la página **crear centro de temas** , puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y administrar los temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="3d338-168">En el cuadro **nombre del sitio** , escriba un nombre para el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="3d338-169">Opcionalmente, puede escribir una descripción breve en el cuadro **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="3d338-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="3d338-170">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3d338-170">Select **Next**.</span></span>

   ![Crear centro de conocimiento](../media/ksetup4.png)  

10. <span data-ttu-id="3d338-172">En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="3d338-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="3d338-173">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="3d338-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="3d338-174">Se mostrará la página de **información de red activada** , confirmando que el sistema empezará a analizar los sitios seleccionados para ver los temas y crear el sitio del centro de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="3d338-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="3d338-175">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="3d338-175">Select **Done**.</span></span>

12. <span data-ttu-id="3d338-176">Se le devolverá a la página **conectar personas a la información** .</span><span class="sxs-lookup"><span data-stu-id="3d338-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="3d338-177">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="3d338-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configuración aplicada](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="3d338-179">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="3d338-179">Assign licenses</span></span>

<span data-ttu-id="3d338-180">Una vez que haya configurado las experiencias de los temas, debe asignar licencias para los usuarios que vayan a usar las experiencias de los temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="3d338-181">Solo los usuarios con una licencia pueden ver información sobre temas como las sugerencias, las tarjetas de temas, las páginas de temas y el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="3d338-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="3d338-182">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="3d338-182">To assign licenses:</span></span>

1. <span data-ttu-id="3d338-183">En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="3d338-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="3d338-184">Seleccione los usuarios a los que desea conceder licencias y haga clic en **Administrar licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="3d338-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="3d338-185">Seleccione **Asignar más**.</span><span class="sxs-lookup"><span data-stu-id="3d338-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="3d338-186">En **licencias**, seleccione **experiencias del tema**.</span><span class="sxs-lookup"><span data-stu-id="3d338-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="3d338-187">En **aplicaciones**, asegúrese de que la **búsqueda de conectores de gráficos con** experiencias de índice y **tema** estén seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="3d338-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3d338-188">![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="3d338-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="3d338-189">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="3d338-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="3d338-190">Administrar experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="3d338-190">Manage topic experiences</span></span>

<span data-ttu-id="3d338-191">Una vez que haya configurado las experiencias de los temas, puede cambiar la configuración que eligió durante la instalación en el [centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="3d338-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="3d338-192">Consulte las siguientes referencias:</span><span class="sxs-lookup"><span data-stu-id="3d338-192">See the following references:</span></span>

- [<span data-ttu-id="3d338-193">Administrar la detección de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d338-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="3d338-194">Administrar la visibilidad de los temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d338-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="3d338-195">Administrar los permisos de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d338-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="3d338-196">Cambiar el nombre del centro de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d338-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="3d338-197">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d338-197">See also</span></span>

[<span data-ttu-id="3d338-198">Información general sobre las experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="3d338-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
