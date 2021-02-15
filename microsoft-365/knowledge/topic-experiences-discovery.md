---
title: Administrar la detección de temas en temas de Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Obtenga información sobre cómo administrar la detección de temas en Temas de Microsoft Viva.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107770"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="0b64d-103">Administrar la detección de temas en temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="0b64d-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="0b64d-104">Puede administrar la configuración de detección de temas en el [Centro de administración de Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0b64d-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="0b64d-105">Debe ser administrador global o administrador de SharePoint para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="0b64d-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="0b64d-106">Para obtener acceso a la configuración de administración de temas:</span><span class="sxs-lookup"><span data-stu-id="0b64d-106">To access topics management settings:</span></span>

1. <span data-ttu-id="0b64d-107">En el Centro de administración de Microsoft 365, haga clic **en Configuración** y, a continuación, en Configuración de **la organización.**</span><span class="sxs-lookup"><span data-stu-id="0b64d-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="0b64d-108">En la **pestaña Servicios,** haga clic en **Experiencias del tema.**</span><span class="sxs-lookup"><span data-stu-id="0b64d-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Conectar a las personas con el conocimiento](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="0b64d-110">Seleccione la **pestaña Detección de** temas. Consulta las siguientes secciones para obtener información sobre cada configuración.</span><span class="sxs-lookup"><span data-stu-id="0b64d-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="0b64d-112">Seleccionar orígenes de temas de SharePoint</span><span class="sxs-lookup"><span data-stu-id="0b64d-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="0b64d-113">Puede cambiar los sitios de SharePoint de su organización que se rastrearán para obtener temas.</span><span class="sxs-lookup"><span data-stu-id="0b64d-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="0b64d-114">Si desea incluir o excluir una lista específica de sitios, puede usar la siguiente plantilla .csv:</span><span class="sxs-lookup"><span data-stu-id="0b64d-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="0b64d-115">Si agrega sitios mediante el selector de sitios, se agregan a la lista existente de sitios para incluir o excluir.</span><span class="sxs-lookup"><span data-stu-id="0b64d-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="0b64d-116">Si carga un archivo .csv, sobrescribirá cualquier lista existente.</span><span class="sxs-lookup"><span data-stu-id="0b64d-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="0b64d-117">Si ya ha incluido o excluido sitios específicos, puede descargar la lista como un archivo .csv, realizar cambios y cargar la nueva lista.</span><span class="sxs-lookup"><span data-stu-id="0b64d-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="0b64d-118">Para elegir sitios para la detección de temas</span><span class="sxs-lookup"><span data-stu-id="0b64d-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="0b64d-119">En la **pestaña Detección** de temas, en Seleccionar orígenes de temas de **SharePoint,** **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="0b64d-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="0b64d-120">En la página Seleccionar orígenes de temas **de SharePoint,** seleccione los sitios de SharePoint que se rastrearán como orígenes de los temas durante la detección.</span><span class="sxs-lookup"><span data-stu-id="0b64d-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="0b64d-121">Incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b64d-121">This includes:</span></span>
    - <span data-ttu-id="0b64d-122">**Todos los sitios:** todos los sitios de SharePoint del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="0b64d-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="0b64d-123">Esto captura los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="0b64d-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="0b64d-124">**Todos, excepto los sitios seleccionados:** escriba los nombres de los sitios que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="0b64d-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="0b64d-125">También puede cargar una lista de sitios en los que desea no participar en la detección.</span><span class="sxs-lookup"><span data-stu-id="0b64d-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="0b64d-126">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="0b64d-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="0b64d-127">**Solo los sitios seleccionados:** escriba los nombres de los sitios que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="0b64d-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="0b64d-128">También puede cargar una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="0b64d-128">You can also upload a list of sites.</span></span> <span data-ttu-id="0b64d-129">Los sitios creados en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="0b64d-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="0b64d-130">**Ningún sitio:** los temas no se generarán ni actualizarán automáticamente con contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0b64d-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="0b64d-131">Los temas existentes permanecen en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="0b64d-131">Existing topics remain in the topic center.</span></span>

    ![Captura de pantalla de la interfaz de usuario de orígenes de temas de SharePoint](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="0b64d-133">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0b64d-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="0b64d-134">Excluir temas por nombre</span><span class="sxs-lookup"><span data-stu-id="0b64d-134">Exclude topics by name</span></span>

<span data-ttu-id="0b64d-135">Puede excluir temas de la detección cargando una lista con un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="0b64d-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="0b64d-136">Si ya ha excluido temas, puede descargar el archivo .csv, realizar cambios y cargarlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0b64d-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="0b64d-137">En la **pestaña Detección** de temas, en **Excluir temas,** **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="0b64d-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="0b64d-138">Haga **clic en Excluir temas por nombre.**</span><span class="sxs-lookup"><span data-stu-id="0b64d-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="0b64d-139">Si necesitas crear una lista, descarga la plantilla .csv y agrega los temas que quieras excluir (consulta Trabajar con la *plantilla .csv a* continuación).</span><span class="sxs-lookup"><span data-stu-id="0b64d-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="0b64d-140">Cuando el archivo esté listo, haga clic **en Examinar** y cargue el archivo.</span><span class="sxs-lookup"><span data-stu-id="0b64d-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="0b64d-141">Si hay una lista existente, puede descargar el archivo .csv que contiene la lista.</span><span class="sxs-lookup"><span data-stu-id="0b64d-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="0b64d-142">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0b64d-142">Click **Save**.</span></span>

    ![Captura de pantalla de la interfaz de usuario de los temas excluidos](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="0b64d-144">Trabajar con la plantilla .csv</span><span class="sxs-lookup"><span data-stu-id="0b64d-144">Working with the .csv template</span></span>

<span data-ttu-id="0b64d-145">Puede copiar la plantilla csv siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b64d-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="0b64d-146">En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:</span><span class="sxs-lookup"><span data-stu-id="0b64d-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="0b64d-147">**Nombre:** escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="0b64d-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="0b64d-148">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="0b64d-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="0b64d-149">Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="0b64d-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="0b64d-150">Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="0b64d-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="0b64d-151">Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como el círculo de *arco,* el arco de *plasma y* el arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que se incluye el texto como parte de una palabra, como *Arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="0b64d-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="0b64d-152">**Significa (opcional):** si desea excluir un acrónimo, escriba las palabras que significa el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="0b64d-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="0b64d-153">**MatchType-Exact/Partial**: Escriba si el nombre que escribió fue *un tipo de* coincidencia exacta *o* parcial.</span><span class="sxs-lookup"><span data-stu-id="0b64d-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Excluir temas de la plantilla CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="0b64d-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b64d-155">See also</span></span>

[<span data-ttu-id="0b64d-156">Administrar la visibilidad de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b64d-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="0b64d-157">Administrar permisos de tema en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b64d-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="0b64d-158">Cambiar el nombre del centro de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b64d-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
