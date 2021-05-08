---
title: 'Próximamente: Configure SharePoint como un origen de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Obtenga información sobre cómo configurar SharePoint como un origen de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fc702f57b75b78ab523226ba7d8a8eb6505f2975
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244144"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="c2c87-103">Próximamente: Configure SharePoint como un origen de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c2c87-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="c2c87-104">La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="c2c87-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="c2c87-105">Puede configurar el SharePoint como un origen de contenido de aprendizaje para que el propio contenido de su organización esté disponible en Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="c2c87-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="c2c87-106">Información general</span><span class="sxs-lookup"><span data-stu-id="c2c87-106">Overview</span></span>

<span data-ttu-id="c2c87-107">El administrador del conocimiento (o administrador global) proporciona una dirección URL del sitio a la que el servicio de aprendizaje puede crear una ubicación centralizada vacía (el repositorio de contenido de la aplicación de aprendizaje) en forma de una lista de SharePoint estructurada.</span><span class="sxs-lookup"><span data-stu-id="c2c87-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="c2c87-108">La organización puede usar esta lista para hospedar vínculos a carpetas entre SharePoint que contienen contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c2c87-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="c2c87-109">Los administradores son responsables de recopilar y comisariar una lista de direcciones URL de carpetas.</span><span class="sxs-lookup"><span data-stu-id="c2c87-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="c2c87-110">Estas carpetas solo deben incluir contenido que pueda estar disponible en Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="c2c87-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="c2c87-111">Viva Learning (versión preliminar) admite los siguientes tipos de documentos:</span><span class="sxs-lookup"><span data-stu-id="c2c87-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="c2c87-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="c2c87-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="c2c87-113">Audio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="c2c87-113">Audio (.m4a)</span></span>
- <span data-ttu-id="c2c87-114">Vídeo (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="c2c87-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="c2c87-115">Para obtener más información, [vea SharePoint límites](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span><span class="sxs-lookup"><span data-stu-id="c2c87-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="c2c87-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="c2c87-116">Permissions</span></span>

<span data-ttu-id="c2c87-117">Las direcciones URL de carpetas de biblioteca de documentos se pueden recopilar SharePoint sitio de la organización.</span><span class="sxs-lookup"><span data-stu-id="c2c87-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="c2c87-118">Viva Learning (versión preliminar) sigue todos los permisos de contenido existentes.</span><span class="sxs-lookup"><span data-stu-id="c2c87-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="c2c87-119">Por lo tanto, solo se puede buscar y ver el contenido para el que un usuario tiene permiso de acceso en Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="c2c87-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="c2c87-120">Cualquier contenido dentro de estas carpetas se puede buscar, pero solo se puede usar el contenido al que el empleado individual tenga permisos.</span><span class="sxs-lookup"><span data-stu-id="c2c87-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="c2c87-121">Actualmente, no se admite la eliminación de contenido del repositorio de la organización.</span><span class="sxs-lookup"><span data-stu-id="c2c87-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="c2c87-122">Para quitar contenido que no se ha presentado de forma involuntarla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c2c87-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="c2c87-123">Para restringir el acceso a la biblioteca de documentos, seleccione la **opción Mostrar acciones** y, a continuación, seleccione Administrar **acceso**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Página de biblioteca de documentos SharePoint muestra la opción Mostrar acciones con Administrar acceso con alta puntuación.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="c2c87-125">Elimine el documento original dentro de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c2c87-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="c2c87-126">Para obtener más información, vea [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="c2c87-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="c2c87-127">Servicio de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="c2c87-127">Learning Service</span></span>

<span data-ttu-id="c2c87-128">El servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas.</span><span class="sxs-lookup"><span data-stu-id="c2c87-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="c2c87-129">En un plazo de 24 horas después de proporcionar la dirección URL de carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de la organización en Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="c2c87-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="c2c87-130">Todos los cambios en el contenido, incluidos los metadatos y permisos actualizados, también se aplicarán en el Servicio de aprendizaje en un plazo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="c2c87-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="c2c87-131">Configurar SharePoint como origen</span><span class="sxs-lookup"><span data-stu-id="c2c87-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="c2c87-132">Debe ser un administrador Microsoft 365 global, SharePoint administrador o administrador de conocimientos para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="c2c87-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="c2c87-133">Para configurar SharePoint como orígenes de contenido de aprendizaje en para Viva Learning (versión preliminar), siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c2c87-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="c2c87-134">En la navegación izquierda del centro Microsoft 365 administración, vaya a **Configuración**  >  **configuración de la organización.**</span><span class="sxs-lookup"><span data-stu-id="c2c87-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="c2c87-135">En la **página Configuración de** la organización, en la pestaña **Servicios,** seleccione **Viva Learning (versión preliminar).**</span><span class="sxs-lookup"><span data-stu-id="c2c87-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Configuración en el Centro Microsoft 365 administración que muestra Viva Learning en la lista.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="c2c87-137">En el panel **Viva Learning (versión** preliminar), en SharePoint, proporciona la dirección URL del sitio al sitio de SharePoint donde desea que Viva Learning (versión preliminar) cree un repositorio centralizado.</span><span class="sxs-lookup"><span data-stu-id="c2c87-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Panel de aprendizaje del centro Microsoft 365 administración que muestra SharePoint seleccionado.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="c2c87-139">Una SharePoint se crea automáticamente en el sitio SharePoint proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c2c87-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Lista de SharePoint creada recientemente en el SharePoint web.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="c2c87-141">En la navegación izquierda del sitio SharePoint, seleccione **Contenido** del sitio Aprendizaje del repositorio de contenido  >  **de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint que muestra la navegación por el contenido del sitio y la sección Repositorio de contenido de la aplicación de aprendizaje.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="c2c87-143">En la **página Repositorio de contenido de** la aplicación de aprendizaje, rellene la lista SharePoint con direcciones URL a las carpetas de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c2c87-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="c2c87-144">Seleccione **Nuevo** para ver el **panel Nuevo** elemento.</span><span class="sxs-lookup"><span data-stu-id="c2c87-144">Select **New** to view the **New item** panel.</span></span> 

       ![Página Repositorio de contenido de aprendizaje SharePoint muestra la opción Nuevo.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="c2c87-146">En el **panel Nuevo elemento,** en el **campo Título,** agregue un nombre de directorio de su elección.</span><span class="sxs-lookup"><span data-stu-id="c2c87-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="c2c87-147">En el **campo Dirección URL de** carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c2c87-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="c2c87-148">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-148">Select **Save**.</span></span>

       ![Nuevo panel de elementos en SharePoint que muestra los campos De título y Dirección URL de carpeta.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="c2c87-150">La **página Repositorio de contenido de** la aplicación de aprendizaje se actualiza con el nuevo contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c2c87-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Página repositorio de contenido de aprendizaje en SharePoint muestra la información actualizada.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="c2c87-152">Para permitir un acceso más amplio al repositorio de contenido de la aplicación de aprendizaje, pronto estará disponible un vínculo a la lista en la interfaz de Viva Learning (versión preliminar), donde los usuarios pueden solicitar acceso y, en última instancia, ayudar a rellenar la lista.</span><span class="sxs-lookup"><span data-stu-id="c2c87-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="c2c87-153">Los propietarios del sitio y los administradores globales tendrán que conceder acceso a la lista.</span><span class="sxs-lookup"><span data-stu-id="c2c87-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="c2c87-154">El acceso es específico de la lista únicamente y no se aplica al sitio donde se almacena la lista.</span><span class="sxs-lookup"><span data-stu-id="c2c87-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="c2c87-155">Para obtener más información, [vea Proporcionar el contenido](#provide-your-own-organizations-content) de su propia organización más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c2c87-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="c2c87-156">Curación de la biblioteca de documentos de dirección URL de carpeta</span><span class="sxs-lookup"><span data-stu-id="c2c87-156">Folder URL document library curation</span></span>

<span data-ttu-id="c2c87-157">Los metadatos predeterminados (como la fecha de modificación, creados por, el nombre del documento, el tipo de contenido y el nombre de la organización) se extraen automáticamente en Viva Learning (versión preliminar) mediante la API de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="c2c87-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="c2c87-158">Para mejorar la detección general y la relevancia de búsqueda del contenido, se recomienda agregar una **columna** Descripción.</span><span class="sxs-lookup"><span data-stu-id="c2c87-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="c2c87-159">Para agregar una **columna Description** a la página de la biblioteca de documentos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c2c87-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="c2c87-160">En la **página Documentos,** seleccione **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="c2c87-161">Seleccione la **opción Mostrar acciones** y, a continuación, seleccione Línea única de **texto**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Página Documentos en SharePoint que muestra las opciones Mostrar acciones con una sola línea de texto resaltada.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="c2c87-163">En el panel **Crear una columna,** en el **campo Nombre,** agregue un nombre descriptivo para la columna.</span><span class="sxs-lookup"><span data-stu-id="c2c87-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="c2c87-164">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-164">Select **Save**.</span></span>

     ![Cree un panel de columnas en SharePoint que muestre el nombre y otros campos.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="c2c87-166">En la **página Documentos,** en la **columna Descripción,** agregue descripciones personalizadas para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="c2c87-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="c2c87-167">Si no se proporciona ninguna descripción, Viva Learning (versión preliminar) proporcionará un mensaje predeterminado que resalta el contenido como de su propia SharePoint biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c2c87-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Página Documentos de SharePoint que muestra las descripciones de la columna Descripción.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="c2c87-169">Proporcionar el contenido de su propia organización</span><span class="sxs-lookup"><span data-stu-id="c2c87-169">Provide your own organization's content</span></span>

<span data-ttu-id="c2c87-170">Los administradores de conocimientos pueden acceder al repositorio de contenido de aplicaciones de aprendizaje de su organización en SharePoint, donde pueden proporcionar referencias a bibliotecas de documentos entre organizaciones.</span><span class="sxs-lookup"><span data-stu-id="c2c87-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="c2c87-171">El contenido de estas bibliotecas aparecerá como contenido de aprendizaje en Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="c2c87-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="c2c87-172">En Viva Learning (versión preliminar), seleccione **Más opciones** (**...**) y, a continuación, **seleccione Configuración**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint de biblioteca que muestra la opción Más opciones y Configuración.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="c2c87-174">En **Configuración**, seleccione **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="c2c87-174">Under **Settings**, select **Permissions**.</span></span>

     ![Configuración página de opciones en SharePoint muestra las opciones Permisos y Comprobar acceso.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="c2c87-176">Seleccione **Comprobar el acceso** para conectarse a la biblioteca centralizada de la organización.</span><span class="sxs-lookup"><span data-stu-id="c2c87-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
