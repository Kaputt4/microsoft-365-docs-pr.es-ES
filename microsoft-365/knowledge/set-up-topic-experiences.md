---
title: Configurar temas de Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Obtenga información sobre cómo configurar temas de Microsoft Viva
ms.openlocfilehash: cc420a0631f5b861341116abcd50cfe90e15450e
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551896"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="d60da-103">Configurar temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d60da-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="d60da-104">Puede usar el Centro de administración de Microsoft 365 para configurar y configurar [temas](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d60da-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="d60da-105">Es importante planear la mejor forma de configurar y configurar temas en el entorno.</span><span class="sxs-lookup"><span data-stu-id="d60da-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="d60da-106">Asegúrese de leer [Plan for Microsoft Viva Topics](plan-topic-experiences.md) antes de comenzar los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="d60da-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="d60da-107">Debe estar suscrito a [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) y ser administrador global o administrador de SharePoint para tener acceso al Centro de administración de Microsoft 365 y configurar Temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="d60da-108">Si ha configurado SharePoint para que [requiera dispositivos administrados,](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)asegúrese de configurar Temas desde un dispositivo administrado.</span><span class="sxs-lookup"><span data-stu-id="d60da-108">If you have configured SharePoint to [require managed devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="d60da-109">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="d60da-109">Video demonstration</span></span>

<span data-ttu-id="d60da-110">En este vídeo se muestra el proceso de configuración de temas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d60da-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="d60da-111">Configurar Temas</span><span class="sxs-lookup"><span data-stu-id="d60da-111">Set up Topics</span></span>

<span data-ttu-id="d60da-112">Para configurar temas</span><span class="sxs-lookup"><span data-stu-id="d60da-112">To set up Topics</span></span>

1. <span data-ttu-id="d60da-113">En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)seleccione **Configurar** y, a continuación, vea la sección **Archivos y** contenido.</span><span class="sxs-lookup"><span data-stu-id="d60da-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="d60da-114">En la **sección Archivos y contenido,** haga clic **en Conectar personas al conocimiento.**</span><span class="sxs-lookup"><span data-stu-id="d60da-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Conectar a las personas con el conocimiento](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="d60da-116">En la **página Conectar personas al conocimiento,** haga clic en Introducción para seguir el proceso de configuración. </span><span class="sxs-lookup"><span data-stu-id="d60da-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Introducción](../media/k-get-started.png) 

4. <span data-ttu-id="d60da-118">En la página Elegir cómo pueden encontrarse los temas de **Viva Topics,** configurará la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="d60da-119">En la sección Seleccionar orígenes de temas **de SharePoint,** seleccione qué sitios de SharePoint se rastrearán como orígenes de los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="d60da-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="d60da-120">Elija entre:</span><span class="sxs-lookup"><span data-stu-id="d60da-120">Choose from:</span></span>
    - <span data-ttu-id="d60da-121">**Todos los sitios:** todos los sitios de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="d60da-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="d60da-122">Esto incluye sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="d60da-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="d60da-123">**Todos, excepto los sitios seleccionados:** escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="d60da-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="d60da-124">También puede cargar una lista de sitios que desea excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="d60da-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="d60da-125">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="d60da-126">**Solo sitios seleccionados:** escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="d60da-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="d60da-127">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="d60da-127">You can also upload a list of sites.</span></span> <span data-ttu-id="d60da-128">Los sitios creados en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="d60da-129">**Sin sitios:** no incluya ningún sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d60da-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Elegir cómo buscar temas](../media/ksetup1.png) 
   
5. <span data-ttu-id="d60da-131">En la **sección Excluir temas por** nombre, puede agregar nombres de los temas que desea excluir de la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="d60da-132">Use esta configuración para evitar que la información confidencial se incluya como temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="d60da-133">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="d60da-133">The options are:</span></span>
    - <span data-ttu-id="d60da-134">**No excluir ningún tema**</span><span class="sxs-lookup"><span data-stu-id="d60da-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="d60da-135">**Excluir temas por nombre**</span><span class="sxs-lookup"><span data-stu-id="d60da-135">**Exclude topics by name**</span></span>

    ![Excluir temas](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="d60da-137">(Los administradores de conocimientos también pueden excluir los temas del centro de temas después de la detección).</span><span class="sxs-lookup"><span data-stu-id="d60da-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="d60da-138">Cómo excluir temas por nombre</span><span class="sxs-lookup"><span data-stu-id="d60da-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="d60da-139">Si necesita excluir temas, después de seleccionar Excluir temas por su **nombre,** descargue la plantilla .csv y actualícelo con la lista de temas que desea excluir de los resultados de detección.</span><span class="sxs-lookup"><span data-stu-id="d60da-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir temas en plantilla CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="d60da-141">En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:</span><span class="sxs-lookup"><span data-stu-id="d60da-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="d60da-142">**Nombre:** escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="d60da-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="d60da-143">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="d60da-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="d60da-144">Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="d60da-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="d60da-145">Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="d60da-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="d60da-146">Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como *Círculo* de arco, *Soldador de arco de* plasma o Arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que el texto se incluye como parte de una palabra, como *Arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="d60da-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="d60da-147">**Significa (opcional):** si desea excluir un acrónimo, escriba las palabras que el acrónimo representa.</span><span class="sxs-lookup"><span data-stu-id="d60da-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="d60da-148">**MatchType-Exact/Partial:** escriba si el nombre que escribió era *un tipo de* coincidencia exacto *o* parcial.</span><span class="sxs-lookup"><span data-stu-id="d60da-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="d60da-149">Después de completar y guardar el archivo .csv, seleccione **Examinar** para buscarlo y seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="d60da-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="d60da-150">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d60da-150">Select **Next**.</span></span>

6. <span data-ttu-id="d60da-151">En la **página Quién puede ver los temas** y dónde pueden verlos, configurará la visibilidad del tema.</span><span class="sxs-lookup"><span data-stu-id="d60da-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="d60da-152">En la configuración Quién **puede ver** temas, elige quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="d60da-153">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="d60da-153">You can select:</span></span>
    - <span data-ttu-id="d60da-154">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="d60da-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d60da-155">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="d60da-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="d60da-156">**Nadie**</span><span class="sxs-lookup"><span data-stu-id="d60da-156">**No one**</span></span>

    ![Quién puede ver temas](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="d60da-158">Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de Experiencias de tema asignadas podrán ver temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="d60da-159">En la **página Permisos para la** administración de temas, elige quién podrá crear, editar o administrar temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="d60da-160">En la **sección Quién puede crear y editar temas,** puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="d60da-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="d60da-161">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="d60da-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d60da-162">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="d60da-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="d60da-163">**Nadie**</span><span class="sxs-lookup"><span data-stu-id="d60da-163">**No one**</span></span>

    ![Permisos para la administración de temas, que pueden crear y editar temas](../media/ksetup3.png) 

8. <span data-ttu-id="d60da-165">En la **sección Quién puede administrar temas,** puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="d60da-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="d60da-166">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="d60da-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d60da-167">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="d60da-167">**Only selected people or security groups**</span></span>

    ![Permisos para la administración de temas](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="d60da-169">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d60da-169">Select **Next**.</span></span>

9. <span data-ttu-id="d60da-170">En la **página Crear centro de** temas, puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y los temas se pueden administrar.</span><span class="sxs-lookup"><span data-stu-id="d60da-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="d60da-171">En el **cuadro Nombre del** sitio, escriba un nombre para el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="d60da-172">Opcionalmente, puede escribir una breve descripción en el **cuadro** Descripción.</span><span class="sxs-lookup"><span data-stu-id="d60da-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="d60da-173">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d60da-173">Select **Next**.</span></span>

   ![Crear centro de conocimiento](../media/ksetup4.png)  

10. <span data-ttu-id="d60da-175">En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="d60da-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="d60da-176">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="d60da-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="d60da-177">Se mostrará la página Temas **de Viva** activada, lo que confirma que el sistema empezará a analizar los sitios seleccionados para los temas y a crear el sitio del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="d60da-178">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="d60da-178">Select **Done**.</span></span>

12. <span data-ttu-id="d60da-179">Se te devolverá a la página **Conectar personas al** conocimiento.</span><span class="sxs-lookup"><span data-stu-id="d60da-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="d60da-180">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="d60da-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configuración aplicada](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="d60da-182">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="d60da-182">Assign licenses</span></span>

<span data-ttu-id="d60da-183">Una vez configuradas las experiencias de temas, debe asignar licencias para los usuarios que usarán Temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-183">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="d60da-184">Solo los usuarios con una licencia pueden ver información sobre temas como resaltados, tarjetas de temas, páginas de temas y el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="d60da-184">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="d60da-185">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="d60da-185">To assign licenses:</span></span>

1. <span data-ttu-id="d60da-186">En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="d60da-186">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="d60da-187">Selecciona los usuarios que quieres licenciar y haz clic **en Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="d60da-187">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="d60da-188">En **Licencias,** seleccione **Temas de Viva**.</span><span class="sxs-lookup"><span data-stu-id="d60da-188">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="d60da-189">En **Aplicaciones,** asegúrate de **que Graph Connectors Search con Index (Temas de Viva)** y Viva **Topics** estén seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d60da-189">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

    ![Licencias de Temas de Microsoft Viva en el Centro de administración de Microsoft 365](../media/topic-experiences-licenses.png)

5. <span data-ttu-id="d60da-191">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="d60da-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="d60da-192">Administrar experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="d60da-192">Manage topic experiences</span></span>

<span data-ttu-id="d60da-193">Una vez configurados los temas, puede cambiar la configuración que eligió durante la instalación en el Centro de administración [de Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="d60da-193">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="d60da-194">Vea las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="d60da-194">See the following references:</span></span>

- [<span data-ttu-id="d60da-195">Administrar la detección de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d60da-195">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="d60da-196">Administrar visibilidad de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d60da-196">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="d60da-197">Administrar permisos de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d60da-197">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="d60da-198">Cambiar el nombre del centro de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="d60da-198">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="d60da-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d60da-199">See also</span></span>

[<span data-ttu-id="d60da-200">Introducción a las experiencias del tema</span><span class="sxs-lookup"><span data-stu-id="d60da-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
