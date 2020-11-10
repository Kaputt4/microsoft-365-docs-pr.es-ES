---
title: 'Configuración de la administración de conocimiento (versión preliminar) '
description: Cómo configurar la administración del conocimiento.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989030"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="2e9b6-103">Configuración de la administración de conocimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="2e9b6-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="2e9b6-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="2e9b6-105">[Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="2e9b6-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="2e9b6-106">Puede usar el centro de administración de Microsoft 365 para instalar y configurar la [Administración del conocimiento](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2e9b6-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="2e9b6-107">Es importante planear la mejor forma de configurar y configurar la administración del conocimiento en su entorno.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="2e9b6-108">Por ejemplo, tendrá que tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="2e9b6-109">Los sitios de SharePoint que desea analizar para los temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="2e9b6-110">Los usuarios a los que desea que los temas sean visibles.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="2e9b6-111">Los usuarios a los que desea conceder permisos para administrar temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="2e9b6-112">Los usuarios a los que desea conceder permisos para crear o editar temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="2e9b6-113">El nombre que desea dar al centro de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="2e9b6-114">Puede que le resulte útil crear grupos de seguridad para asignar a los usuarios los permisos necesarios para ver temas, administrar temas y crear y editar temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="2e9b6-115">Un administrador también puede [realizar cambios en la configuración seleccionada en cualquier momento después](topic-experiences-discovery.md) de la instalación mediante la configuración de administración de conocimiento en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e9b6-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="2e9b6-116">Requirements</span></span> 
<span data-ttu-id="2e9b6-117">Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y configurar las tareas de conocimiento de la organización.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="2e9b6-118">Configurar la red de conocimientos</span><span class="sxs-lookup"><span data-stu-id="2e9b6-118">Set up your knowledge network</span></span>

<span data-ttu-id="2e9b6-119">La configuración de la red de conocimientos le guiará a través de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="2e9b6-120">Detección de temas: selección de los temas y orígenes del tema que se deben excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="2e9b6-121">Visibilidad del tema: seleccionar quién puede ver los temas como puntos destacados, en las páginas de búsqueda y de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="2e9b6-122">Topic Permissions: seleccionar quién puede crear, editar y administrar temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="2e9b6-123">Centro de temas: cree su centro de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="2e9b6-124">Revisión: Compruebe y aplique la configuración.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="2e9b6-125">Para configurar la red de conocimientos:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="2e9b6-126">En el centro de administración de Microsoft 365 (admin.microsoft.com), seleccione **instalación** y, a continuación, ver la sección de conocimientos de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="2e9b6-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="2e9b6-127">En la sección conocimientos de la **organización** , haga clic en **conectar personas con el conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Conectar a personas con el conocimiento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="2e9b6-129">En la página **conectar personas a los conocimientos** , **haga clic en introducción para** guiarlo en el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Introducción](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="2e9b6-131">En la página **elegir el modo en que la red de conocimiento puede buscar temas** , se configurará la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="2e9b6-132">En la sección **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="2e9b6-133">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-133">This includes:</span></span></br>
    <span data-ttu-id="2e9b6-134">a.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-134">a.</span></span> <span data-ttu-id="2e9b6-135">**Todos los sitios** : todos los sitios de SharePoint de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="2e9b6-136">Esto captura los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="2e9b6-137">b.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-137">b.</span></span> <span data-ttu-id="2e9b6-138">**Todos, excepto los sitios seleccionados** : escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="2e9b6-139">También puede cargar una lista de sitios que desea excluir de la detección.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="2e9b6-140">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="2e9b6-141">c.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-141">c.</span></span> <span data-ttu-id="2e9b6-142">**Solo sitios seleccionados** : escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="2e9b6-143">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-143">You can also upload a list of sites.</span></span> <span data-ttu-id="2e9b6-144">Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Elegir cómo buscar temas](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="2e9b6-146">En la sección **excluir temas por nombre** , puede elegir incluir los nombres de los temas que no desea que se incluyan en los resultados detectados.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="2e9b6-147">Use esta opción para evitar que se incluyan temas confidenciales como parte de la red de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="2e9b6-148">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-148">Your options include:</span></span></br>
    <span data-ttu-id="2e9b6-149">a.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-149">a.</span></span> <span data-ttu-id="2e9b6-150">**No excluir temas**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="2e9b6-151">b.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-151">b.</span></span> <span data-ttu-id="2e9b6-152">**Excluir temas por nombre** : Si tiene temas que no desea que se muestren a los usuarios como parte de la red de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![Excluir temas](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="2e9b6-154">Cómo excluir temas por nombre</span><span class="sxs-lookup"><span data-stu-id="2e9b6-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="2e9b6-155">Si necesita excluir temas, después de seleccionar **excluir temas por nombre** , seleccione **descargar la plantilla. csv**.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="2e9b6-156">Use el Excel. Plantilla CSV para incluir una lista de temas que desea excluir de los resultados de la detección.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir temas en la plantilla CSV](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="2e9b6-158">En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="2e9b6-159">**Name** : escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="2e9b6-160">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="2e9b6-161">Coincidencia exacta: puede incluir el acrónimo o el nombre exacto (por ejemplo, *contoso* o *ATL* ).</span><span class="sxs-lookup"><span data-stu-id="2e9b6-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="2e9b6-162">Coincidencia parcial: puede excluir todos los temas que contengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="2e9b6-163">Por ejemplo, *arco* excluirá todos los temas que contengan la palabra *Arc* , como *círculo arco* , *soldadura de arco de plasma* o arco de *formación*. Tenga en cuenta que no se excluirán los temas en los que se incluya el texto como parte de una palabra, como la *arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="2e9b6-164">**Expansión (opcional)** : Si desea excluir un acrónimo, escriba las palabras que representa el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="2e9b6-165">**MatchType-Exact/Partial** : escriba si el nombre que ha escrito es un tipo de coincidencia *exacta* o *parcial* .</span><span class="sxs-lookup"><span data-stu-id="2e9b6-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="2e9b6-166">Una vez que haya completado y guardado el archivo de plantilla CSV, seleccione **examinar** para localizarlo y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="2e9b6-167">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="2e9b6-168">En la página **quién puede ver los temas y dónde pueden verlos** , configurará la visibilidad de los temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="2e9b6-169">En los **temas quién puede ver en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="2e9b6-170">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-170">You can select:</span></span></br>
    <span data-ttu-id="2e9b6-171">a.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-171">a.</span></span> <span data-ttu-id="2e9b6-172">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="2e9b6-173">b.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-173">b.</span></span> <span data-ttu-id="2e9b6-174">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="2e9b6-175">c.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-175">c.</span></span> <span data-ttu-id="2e9b6-176">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-176">**No one**</span></span></br>

    ![Quién puede ver los temas](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="2e9b6-178">Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de administración de conocimiento podrán ver los temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="2e9b6-179">En la página **permisos para la administración de temas** , elija quién podrá crear, editar o administrar temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="2e9b6-180">En la sección **quién puede crear y editar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="2e9b6-181">a.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-181">a.</span></span> <span data-ttu-id="2e9b6-182">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="2e9b6-183">b.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-183">b.</span></span> <span data-ttu-id="2e9b6-184">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="2e9b6-185">En la sección **quién puede administrar temas** , puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="2e9b6-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="2e9b6-186">a.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-186">a.</span></span> <span data-ttu-id="2e9b6-187">**Todos en su organización**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="2e9b6-188">b.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-188">b.</span></span> <span data-ttu-id="2e9b6-189">**Personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="2e9b6-189">**Selected people or security groups**</span></span></br>

    ![Permisos para la administración de temas](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="2e9b6-191">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="2e9b6-192">En la página **crear centro de temas** , puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y administrar los temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="2e9b6-193">En el cuadro **nombre del centro de temas** , escriba un nombre para el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="2e9b6-194">Opcionalmente, puede escribir una breve descripción en el cuadro **Descripción del sitio** .</span><span class="sxs-lookup"><span data-stu-id="2e9b6-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="2e9b6-195">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-195">Select **Next**.</span></span></br>

   ![Crear centro de conocimiento](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="2e9b6-197">En la página **Revisar y finalizar** , puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2e9b6-198">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Finalizar y revisar](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="2e9b6-200">Se mostrará la página de **información de red activada** , confirmando que el sistema empezará a analizar los sitios seleccionados para ver los temas y crear el sitio del centro de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="2e9b6-201">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-201">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="2e9b6-203">Se le devolverá a la página **conectar personas a la información** .</span><span class="sxs-lookup"><span data-stu-id="2e9b6-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="2e9b6-204">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configuración aplicada](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="2e9b6-206">Después de la instalación, un administrador puede [realizar cambios en la configuración de administración de conocimiento](topic-experiences-discovery.md) que haya seleccionado en cualquier momento volviendo a esta p? gina.</span><span class="sxs-lookup"><span data-stu-id="2e9b6-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="2e9b6-207">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e9b6-207">See also</span></span>



  






