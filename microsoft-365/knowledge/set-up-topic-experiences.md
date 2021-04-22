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
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930226"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="08a35-103">Configurar temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="08a35-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="08a35-104">Puede usar el Centro de administración de Microsoft 365 para configurar y configurar [temas](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="08a35-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="08a35-105">Es importante planear la mejor forma de configurar y configurar temas en el entorno.</span><span class="sxs-lookup"><span data-stu-id="08a35-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="08a35-106">Asegúrese de leer [Plan for Microsoft Viva Topics](plan-topic-experiences.md) antes de comenzar los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="08a35-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="08a35-107">Debe estar suscrito a [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) y ser administrador global o administrador de SharePoint para tener acceso al Centro de administración de Microsoft 365 y configurar Temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="08a35-108">Si ha configurado SharePoint para que [requiera dispositivos administrados,](/sharepoint/control-access-from-unmanaged-devices)asegúrese de configurar Temas desde un dispositivo administrado.</span><span class="sxs-lookup"><span data-stu-id="08a35-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="08a35-109">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="08a35-109">Video demonstration</span></span>

<span data-ttu-id="08a35-110">En este vídeo se muestra el proceso de configuración de temas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08a35-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="08a35-111">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="08a35-111">Assign licenses</span></span>

<span data-ttu-id="08a35-112">Debe asignar licencias para los usuarios que usarán Temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="08a35-113">Solo los usuarios con una licencia pueden ver información sobre temas como resaltados, tarjetas de temas, páginas de temas y el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="08a35-114">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="08a35-114">To assign licenses:</span></span>

1. <span data-ttu-id="08a35-115">En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="08a35-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="08a35-116">Selecciona los usuarios que quieres licenciar y haz clic **en Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="08a35-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="08a35-117">En **Licencias,** seleccione **Temas de Viva**.</span><span class="sxs-lookup"><span data-stu-id="08a35-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="08a35-118">En **Aplicaciones,** asegúrate de **que Graph Connectors Search con Index (Temas de Viva)** y Viva **Topics** estén seleccionados.</span><span class="sxs-lookup"><span data-stu-id="08a35-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08a35-119">![Licencias de Temas de Microsoft Viva en el Centro de administración de Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="08a35-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="08a35-120">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="08a35-120">Click **Save changes**.</span></span>

<span data-ttu-id="08a35-121">Los usuarios pueden tardar hasta una hora en obtener acceso a temas después de asignar las licencias.</span><span class="sxs-lookup"><span data-stu-id="08a35-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="08a35-122">Configurar Temas</span><span class="sxs-lookup"><span data-stu-id="08a35-122">Set up Topics</span></span>

<span data-ttu-id="08a35-123">Para configurar temas</span><span class="sxs-lookup"><span data-stu-id="08a35-123">To set up Topics</span></span>

1. <span data-ttu-id="08a35-124">En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)seleccione **Configurar** y, a continuación, vea la sección **Archivos y** contenido.</span><span class="sxs-lookup"><span data-stu-id="08a35-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="08a35-125">En la **sección Archivos y contenido,** haga clic **en Conectar personas al conocimiento.**</span><span class="sxs-lookup"><span data-stu-id="08a35-125">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Conectar a las personas con el conocimiento](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="08a35-127">En la **página Conectar personas al conocimiento,** haga clic en Introducción para seguir el proceso de configuración. </span><span class="sxs-lookup"><span data-stu-id="08a35-127">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Comenzar](../media/k-get-started.png) 

4. <span data-ttu-id="08a35-129">En la página Elegir cómo pueden encontrarse los temas de **Viva Topics,** configurará la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-129">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="08a35-130">En la sección Seleccionar orígenes de temas **de SharePoint,** seleccione qué sitios de SharePoint se rastrearán como orígenes de los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="08a35-130">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="08a35-131">Elija entre:</span><span class="sxs-lookup"><span data-stu-id="08a35-131">Choose from:</span></span>
    - <span data-ttu-id="08a35-132">**Todos los sitios:** todos los sitios de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="08a35-132">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="08a35-133">Esto incluye sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="08a35-133">This includes current and future sites.</span></span>
    - <span data-ttu-id="08a35-134">**Todos, excepto los sitios seleccionados:** escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="08a35-134">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="08a35-135">También puede cargar una lista de sitios que desea excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="08a35-135">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="08a35-136">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-136">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="08a35-137">**Solo sitios seleccionados:** escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="08a35-137">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="08a35-138">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="08a35-138">You can also upload a list of sites.</span></span> <span data-ttu-id="08a35-139">Los sitios creados en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-139">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="08a35-140">**Sin sitios:** no incluya ningún sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="08a35-140">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Elegir cómo buscar temas](../media/ksetup1.png) 
   
5. <span data-ttu-id="08a35-142">En la **sección Excluir temas por** nombre, puede agregar nombres de los temas que desea excluir de la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-142">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="08a35-143">Use esta configuración para evitar que la información confidencial se incluya como temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-143">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="08a35-144">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="08a35-144">The options are:</span></span>
    - <span data-ttu-id="08a35-145">**No excluir ningún tema**</span><span class="sxs-lookup"><span data-stu-id="08a35-145">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="08a35-146">**Excluir temas por nombre**</span><span class="sxs-lookup"><span data-stu-id="08a35-146">**Exclude topics by name**</span></span>

    ![Excluir temas](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="08a35-148">(Los administradores de conocimientos también pueden excluir los temas del centro de temas después de la detección).</span><span class="sxs-lookup"><span data-stu-id="08a35-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="08a35-149">Cómo excluir temas por nombre</span><span class="sxs-lookup"><span data-stu-id="08a35-149">How to exclude topics by name</span></span>    

    <span data-ttu-id="08a35-150">Si necesita excluir temas, después de seleccionar Excluir temas por su **nombre,** descargue la plantilla .csv y actualícelo con la lista de temas que desea excluir de los resultados de detección.</span><span class="sxs-lookup"><span data-stu-id="08a35-150">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir temas en plantilla CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="08a35-152">En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:</span><span class="sxs-lookup"><span data-stu-id="08a35-152">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="08a35-153">**Nombre:** escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="08a35-153">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="08a35-154">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="08a35-154">There are two ways to do this:</span></span>
        - <span data-ttu-id="08a35-155">Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="08a35-155">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="08a35-156">Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="08a35-156">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="08a35-157">Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como *Círculo* de arco, *Soldador de arco de* plasma o Arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que el texto se incluye como parte de una palabra, como *Arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="08a35-157">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="08a35-158">**Significa (opcional):** si desea excluir un acrónimo, escriba las palabras que el acrónimo representa.</span><span class="sxs-lookup"><span data-stu-id="08a35-158">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="08a35-159">**MatchType-Exact/Partial:** escriba si el nombre que escribió era *un tipo de* coincidencia exacto *o* parcial.</span><span class="sxs-lookup"><span data-stu-id="08a35-159">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="08a35-160">Después de completar y guardar el archivo .csv, seleccione **Examinar** para buscarlo y seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="08a35-160">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="08a35-161">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="08a35-161">Select **Next**.</span></span>

6. <span data-ttu-id="08a35-162">En la **página Quién puede ver los temas** y dónde pueden verlos, configurará la visibilidad del tema.</span><span class="sxs-lookup"><span data-stu-id="08a35-162">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="08a35-163">En la configuración Quién **puede ver** temas, elige quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-163">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="08a35-164">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="08a35-164">You can select:</span></span>
    - <span data-ttu-id="08a35-165">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="08a35-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="08a35-166">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="08a35-166">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="08a35-167">**Nadie**</span><span class="sxs-lookup"><span data-stu-id="08a35-167">**No one**</span></span>

    ![Quién puede ver temas](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="08a35-169">Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de Experiencias de tema asignadas podrán ver temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-169">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="08a35-170">En la **página Permisos para la** administración de temas, elige quién podrá crear, editar o administrar temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-170">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="08a35-171">En la **sección Quién puede crear y editar temas,** puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="08a35-171">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="08a35-172">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="08a35-172">**Everyone in my organization**</span></span>
    - <span data-ttu-id="08a35-173">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="08a35-173">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="08a35-174">**Nadie**</span><span class="sxs-lookup"><span data-stu-id="08a35-174">**No one**</span></span>

    ![Permisos para la administración de temas, que pueden crear y editar temas](../media/ksetup3.png) 

8. <span data-ttu-id="08a35-176">En la **sección Quién puede administrar temas,** puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="08a35-176">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="08a35-177">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="08a35-177">**Everyone in my organization**</span></span>
    - <span data-ttu-id="08a35-178">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="08a35-178">**Only selected people or security groups**</span></span>

    ![Permisos para la administración de temas](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="08a35-180">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="08a35-180">Select **Next**.</span></span>

9. <span data-ttu-id="08a35-181">En la **página Crear centro de** temas, puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y los temas se pueden administrar.</span><span class="sxs-lookup"><span data-stu-id="08a35-181">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="08a35-182">En el **cuadro Nombre del** sitio, escriba un nombre para el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-182">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="08a35-183">Opcionalmente, puede escribir una breve descripción en el **cuadro** Descripción.</span><span class="sxs-lookup"><span data-stu-id="08a35-183">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="08a35-184">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="08a35-184">Select **Next**.</span></span>

   ![Crear centro de conocimiento](../media/ksetup4.png)  

10. <span data-ttu-id="08a35-186">En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="08a35-186">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="08a35-187">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="08a35-187">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="08a35-188">Se mostrará la página Temas **de Viva** activada, lo que confirma que el sistema empezará a analizar los sitios seleccionados para los temas y a crear el sitio del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-188">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="08a35-189">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="08a35-189">Select **Done**.</span></span>

12. <span data-ttu-id="08a35-190">Se te devolverá a la página **Conectar personas al** conocimiento.</span><span class="sxs-lookup"><span data-stu-id="08a35-190">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="08a35-191">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="08a35-191">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configuración aplicada](../media/ksetup7.png)    

<span data-ttu-id="08a35-193">Tenga en cuenta que la primera vez que se habilita la detección de temas, puede tardar hasta dos semanas en que todos los temas sugeridos aparezcan en la vista Administrar temas.</span><span class="sxs-lookup"><span data-stu-id="08a35-193">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="08a35-194">La detección de temas continúa a medida que se realizan nuevas actualizaciones o contenido.</span><span class="sxs-lookup"><span data-stu-id="08a35-194">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="08a35-195">Es normal que haya variaciones en el número de temas sugeridos en su organización mientras Viva Topics evalúa nueva información.</span><span class="sxs-lookup"><span data-stu-id="08a35-195">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="08a35-196">Administrar experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="08a35-196">Manage topic experiences</span></span>

<span data-ttu-id="08a35-197">Una vez configurados los temas, puede cambiar la configuración que eligió durante la instalación en el Centro de administración [de Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="08a35-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="08a35-198">Vea las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="08a35-198">See the following references:</span></span>

- [<span data-ttu-id="08a35-199">Administrar la detección de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="08a35-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="08a35-200">Administrar visibilidad de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="08a35-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="08a35-201">Administrar permisos de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="08a35-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="08a35-202">Cambiar el nombre del centro de temas en Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="08a35-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="08a35-203">Ver también</span><span class="sxs-lookup"><span data-stu-id="08a35-203">See also</span></span>

[<span data-ttu-id="08a35-204">Introducción a las experiencias del tema</span><span class="sxs-lookup"><span data-stu-id="08a35-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
