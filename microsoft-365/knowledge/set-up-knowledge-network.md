---
title: 'Configuración de la administración de conocimiento (versión preliminar) '
description: Cómo configurar la administración del conocimiento.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612553"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="c53e9-103">Configuración de la administración de conocimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c53e9-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c53e9-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="c53e9-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c53e9-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c53e9-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c53e9-106">Puede usar el centro de administración de Microsoft 365 para instalar y configurar la [Administración del conocimiento](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c53e9-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="c53e9-107">Es importante planear la mejor forma de configurar y configurar la administración del conocimiento en su entorno.</span><span class="sxs-lookup"><span data-stu-id="c53e9-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="c53e9-108">Por ejemplo, tendrá que tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c53e9-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="c53e9-109">Los sitios de SharePoint que desea analizar para los temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="c53e9-110">Los usuarios a los que desea que los temas sean visibles.</span><span class="sxs-lookup"><span data-stu-id="c53e9-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="c53e9-111">Los usuarios a los que desea conceder permisos para administrar temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="c53e9-112">Los usuarios a los que desea conceder permisos para crear o editar temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="c53e9-113">El nombre que desea dar al centro de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="c53e9-114">Puede que le resulte útil crear grupos de seguridad para asignar a los usuarios los permisos necesarios para ver temas, administrar temas y crear y editar temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="c53e9-115">Un administrador también puede [realizar cambios en la configuración seleccionada en cualquier momento después](manage-knowledge-network.md) de la instalación mediante la configuración de administración de conocimiento en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c53e9-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="c53e9-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="c53e9-116">Requirements</span></span> 
<span data-ttu-id="c53e9-117">Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y configurar las tareas de conocimiento de la organización.</span><span class="sxs-lookup"><span data-stu-id="c53e9-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="c53e9-118">Configurar la red de conocimientos</span><span class="sxs-lookup"><span data-stu-id="c53e9-118">Set up your knowledge network</span></span>

<span data-ttu-id="c53e9-119">La configuración de la red de conocimientos le guiará a través de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c53e9-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="c53e9-120">Detección de temas: selección de los temas y orígenes del tema que se deben excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="c53e9-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="c53e9-121">Visibilidad del tema: seleccionar quién puede ver los temas como puntos destacados, en las páginas de búsqueda y de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="c53e9-122">Topic Permissions: seleccionar quién puede crear, editar y administrar temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="c53e9-123">Centro de temas: cree su centro de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="c53e9-124">Revisión: Compruebe y aplique la configuración.</span><span class="sxs-lookup"><span data-stu-id="c53e9-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="c53e9-125">Para configurar la red de conocimientos:</span><span class="sxs-lookup"><span data-stu-id="c53e9-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="c53e9-126">En el centro de administración de Microsoft 365 (admin.microsoft.com), seleccione **instalación**y, a continuación, ver la sección de conocimientos de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="c53e9-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="c53e9-127">En la sección conocimientos de la **organización** , haga clic en **conectar personas con el conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="c53e9-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Conectar a personas con el conocimiento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="c53e9-129">En la página **conectar personas a los conocimientos** , **haga clic en introducción para** guiarlo en el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="c53e9-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Introducción](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="c53e9-131">En la página **elegir el modo en que la red de conocimiento puede buscar temas** , se configurará la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="c53e9-132">En la sección **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="c53e9-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="c53e9-133">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="c53e9-133">This includes:</span></span></br>
    <span data-ttu-id="c53e9-134">a.</span><span class="sxs-lookup"><span data-stu-id="c53e9-134">a.</span></span> <span data-ttu-id="c53e9-135">**Todos los sitios**: todos los sitios de SharePoint de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c53e9-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="c53e9-136">Esto captura los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="c53e9-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="c53e9-137">b.</span><span class="sxs-lookup"><span data-stu-id="c53e9-137">b.</span></span> <span data-ttu-id="c53e9-138">**Todos, excepto los sitios seleccionados**: escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="c53e9-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="c53e9-139">También puede cargar una lista de sitios que desea excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="c53e9-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="c53e9-140">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="c53e9-141">c.</span><span class="sxs-lookup"><span data-stu-id="c53e9-141">c.</span></span> <span data-ttu-id="c53e9-142">**Solo sitios seleccionados**: escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="c53e9-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="c53e9-143">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="c53e9-143">You can also upload a list of sites.</span></span> <span data-ttu-id="c53e9-144">Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Elegir cómo buscar temas](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="c53e9-146">En la sección **excluir temas por nombre** , puede elegir incluir los nombres de los temas que no desea que se incluyan en los resultados detectados.</span><span class="sxs-lookup"><span data-stu-id="c53e9-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="c53e9-147">Use esta opción para evitar que se incluyan temas confidenciales como parte de la red de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="c53e9-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="c53e9-148">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="c53e9-148">Your options include:</span></span></br>
    <span data-ttu-id="c53e9-149">a.</span><span class="sxs-lookup"><span data-stu-id="c53e9-149">a.</span></span> <span data-ttu-id="c53e9-150">**No excluir temas**</span><span class="sxs-lookup"><span data-stu-id="c53e9-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="c53e9-151">b.</span><span class="sxs-lookup"><span data-stu-id="c53e9-151">b.</span></span> <span data-ttu-id="c53e9-152">**Excluya el tema que contenga estos términos**: Si tiene temas que no desea que se muestren a los usuarios como parte de la red de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="c53e9-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="c53e9-153">-Descargar la plantilla proporcionada.</span><span class="sxs-lookup"><span data-stu-id="c53e9-153">- Download the provided template.</span></span>
   <span data-ttu-id="c53e9-154">-Escriba los nombres de los temas que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="c53e9-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="c53e9-155">Debe indicar el tipo de coincidencia como exacto o parcial.</span><span class="sxs-lookup"><span data-stu-id="c53e9-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="c53e9-156">Coincidencia exacta significa que los temas que se ajustan al término exacto se excluirán.</span><span class="sxs-lookup"><span data-stu-id="c53e9-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="c53e9-157">La coincidencia parcial es más estricta y significa que se excluirán los temas que contengan el término.</span><span class="sxs-lookup"><span data-stu-id="c53e9-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="c53e9-158">Por ejemplo, si escribe *doc* como nombre de tema, se excluirá el *ensamblado de doc* mientras que el *acoplador* no.</span><span class="sxs-lookup"><span data-stu-id="c53e9-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="c53e9-159">Los nombres de los temas no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="c53e9-160">-Seleccione  **+**   para importar el archivo CSV completado.</span><span class="sxs-lookup"><span data-stu-id="c53e9-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="c53e9-161">A continuación, seleccione **cargar**.</span><span class="sxs-lookup"><span data-stu-id="c53e9-161">Then select **Upload**.</span></span> <span data-ttu-id="c53e9-162">Verá una marca de verificación verde si el archivo se ha procesado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c53e9-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="c53e9-163">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c53e9-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="c53e9-164">En la página **quién puede ver los temas y dónde pueden verlos** , configurará la visibilidad de los temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="c53e9-165">En los **temas quién puede ver en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="c53e9-166">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="c53e9-166">You can select:</span></span></br>
    <span data-ttu-id="c53e9-167">a.</span><span class="sxs-lookup"><span data-stu-id="c53e9-167">a.</span></span> <span data-ttu-id="c53e9-168">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="c53e9-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c53e9-169">b.</span><span class="sxs-lookup"><span data-stu-id="c53e9-169">b.</span></span> <span data-ttu-id="c53e9-170">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="c53e9-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="c53e9-171">c.</span><span class="sxs-lookup"><span data-stu-id="c53e9-171">c.</span></span> <span data-ttu-id="c53e9-172">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="c53e9-172">**No one**</span></span></br>

    ![Quién puede ver los temas](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="c53e9-174">Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de administración de conocimiento podrán ver los temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="c53e9-175">En la página **permisos para la administración de temas** , elija quién podrá crear, editar o administrar temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="c53e9-176">En la sección **quién puede crear y editar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="c53e9-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="c53e9-177">a.</span><span class="sxs-lookup"><span data-stu-id="c53e9-177">a.</span></span> <span data-ttu-id="c53e9-178">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="c53e9-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c53e9-179">b.</span><span class="sxs-lookup"><span data-stu-id="c53e9-179">b.</span></span> <span data-ttu-id="c53e9-180">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="c53e9-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="c53e9-181">En la sección **quién puede administrar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="c53e9-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="c53e9-182">a.</span><span class="sxs-lookup"><span data-stu-id="c53e9-182">a.</span></span> <span data-ttu-id="c53e9-183">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="c53e9-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c53e9-184">b.</span><span class="sxs-lookup"><span data-stu-id="c53e9-184">b.</span></span> <span data-ttu-id="c53e9-185">**Personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="c53e9-185">**Selected people or security groups**</span></span></br>

    ![Permisos para la administración de temas](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="c53e9-187">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c53e9-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="c53e9-188">En la página **crear centro de temas** , puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y administrar los temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="c53e9-189">En el cuadro **nombre del centro de temas** , escriba un nombre para el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="c53e9-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="c53e9-190">Opcionalmente, puede escribir una breve descripción en el cuadro **Descripción del sitio** .</span><span class="sxs-lookup"><span data-stu-id="c53e9-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="c53e9-191">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c53e9-191">Select **Next**.</span></span></br>

   ![Crear centro de conocimiento](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="c53e9-193">En la página **revisar y finalizar** , puede mirar la configuración seleccionada y elegir realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="c53e9-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="c53e9-194">Si está satisfecho con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="c53e9-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Finalizar y revisar](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="c53e9-196">Se mostrará la página de **información de red activada** , confirmando que el sistema empezará a analizar los sitios seleccionados para ver los temas y crear el sitio del centro de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="c53e9-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="c53e9-197">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="c53e9-197">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="c53e9-199">Se le devolverá a la página **conectar personas a la información** .</span><span class="sxs-lookup"><span data-stu-id="c53e9-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="c53e9-200">En esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="c53e9-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configuración aplicada](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="c53e9-202">Después de la instalación, un administrador puede [realizar cambios en la configuración de administración de conocimiento](manage-knowledge-network.md) que haya seleccionado en cualquier momento volviendo a esta p? gina.</span><span class="sxs-lookup"><span data-stu-id="c53e9-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="c53e9-203">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c53e9-203">See also</span></span>



  






