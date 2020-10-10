---
title: Configurar SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Establecer la comprensión del contenido en el Project Cortex.
ms.openlocfilehash: 8217630d66a097fcc714be80bd4d3dcceb623370
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413715"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="0ea00-103">Configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0ea00-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="0ea00-104">Los administradores pueden usar el Centro de administración de Microsoft 365 para configurar [Microsoft SharePoint Syntex](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0ea00-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](document-understanding-overview.md).</span></span> 

<span data-ttu-id="0ea00-105">Considere lo siguiente antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="0ea00-105">Consider the following before you start:</span></span>

- <span data-ttu-id="0ea00-106">¿Qué sitios de SharePoint habilitarán el procesamiento de formularios?</span><span class="sxs-lookup"><span data-stu-id="0ea00-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="0ea00-107">¿Todos ellos, algunos, o seleccionar sitios?</span><span class="sxs-lookup"><span data-stu-id="0ea00-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="0ea00-108">¿Qué nombre le pondrá a su centro de contenido predeterminado?</span><span class="sxs-lookup"><span data-stu-id="0ea00-108">What will you name of your default content center?</span></span>

<span data-ttu-id="0ea00-109">Puede cambiar su configuración después de la configuración inicial en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ea00-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="0ea00-110">El contenido de este artículo es para la vista previa del Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="0ea00-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="0ea00-111">[Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="0ea00-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="0ea00-112">Antes de la configuración, asegúrese de planificar la mejor manera de configurar la comprensión del contenido en su entorno.</span><span class="sxs-lookup"><span data-stu-id="0ea00-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="0ea00-113">Por ejemplo, es necesario hacer consideraciones sobre los siguientes nombres de:</span><span class="sxs-lookup"><span data-stu-id="0ea00-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="0ea00-114">Los sitios de SharePoint que desea habilitar para el procesamiento de formularios: todos ellos, algunos, o sitios seleccionados</span><span class="sxs-lookup"><span data-stu-id="0ea00-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="0ea00-115">Su centro de contenido y el nombre del administrador principal del sitio</span><span class="sxs-lookup"><span data-stu-id="0ea00-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="0ea00-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="0ea00-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="0ea00-117">Debe tener permisos de administrador global o de administrador de SharePoint para poder acceder al Centro de administración de Microsoft 365 y configurar la comprensión del contenido.</span><span class="sxs-lookup"><span data-stu-id="0ea00-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="0ea00-118">Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la configuración, y a lo largo de la comprensión del contenido de la configuración de administración en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ea00-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="0ea00-119">Para configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0ea00-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="0ea00-120">En el Centro de administración de Microsoft 365, seleccione **Configuración** y luego vea la sección **Archivos y contenido**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="0ea00-121">En la sección **Archivos y contenido**, seleccione **Automatizar la comprensión del contenido**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-121">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="0ea00-122">En la página para **Automatizar la comprensión del contenido**, haga clic en **Introducción** para recorrer el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="0ea00-122">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Iniciar la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="0ea00-124">En la página **Configurar el procesamiento** de formularios, puede elegir si desea que los usuarios puedan crear modelos de procesamiento de formularios en bibliotecas de documentos específicos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0ea00-124">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="0ea00-125">En la cinta de opciones de la biblioteca de documentos estará disponible una opción de menú para **Crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="0ea00-125">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="0ea00-126">Para **Qué bibliotecas de SharePoint debe mostrar la opción de crear un modelo de procesamiento de formularios**, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="0ea00-126">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="0ea00-127">**Todas las bibliotecas de SharePoint** para que estén disponibles para todas las bibliotecas de SharePoint de su organización.</span><span class="sxs-lookup"><span data-stu-id="0ea00-127">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="0ea00-128">**Sólo las bibliotecas de los sitios seleccionados**, y luego seleccione los sitios en los que desea que esté disponible o cargue una lista de hasta 50 sitios.</span><span class="sxs-lookup"><span data-stu-id="0ea00-128">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="0ea00-129">**No hay bibliotecas de SharePoint** si no quiere que esté disponible para ningún sitio (puede cambiar esto después de la configuración).</span><span class="sxs-lookup"><span data-stu-id="0ea00-129">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![Configurar el procesamiento del formulario](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="0ea00-131">Quitando un sitio después de incluirlo no afecta a los modelos existentes aplicados a las bibliotecas de ese sitio ni a la capacidad de aplicar modelos de comprensión de documentos a una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0ea00-131">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="0ea00-p105">En la página **Crear centro de contenido**, puede crear un sitio de centro de contenido de SharePoint en el que sus usuarios puedan crear y administrar modelos de comprensión de documentos. </span><span class="sxs-lookup"><span data-stu-id="0ea00-p105">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models. </span></span></br>
    <span data-ttu-id="0ea00-133">a.</span><span class="sxs-lookup"><span data-stu-id="0ea00-133">a.</span></span> <span data-ttu-id="0ea00-134">Para el **Nombre del sitio**, escriba el nombre que quiere darle a su sitio de centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="0ea00-134">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="0ea00-135">b.</span><span class="sxs-lookup"><span data-stu-id="0ea00-135">b.</span></span> <span data-ttu-id="0ea00-136">La **Dirección del sitio** mostrará el URL de su sitio, basado en lo que usted seleccionó para el nombre del sitio.</span><span class="sxs-lookup"><span data-stu-id="0ea00-136">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="0ea00-137">Si desea cambiar la configuración, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-137">If you want to change it, click **Edit**.</span></span></br>

      ![Crear el centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="0ea00-139">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-139">Select **Next**.</span></span>

6. <span data-ttu-id="0ea00-140">En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="0ea00-140">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="0ea00-141">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-141">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="0ea00-142">En la página de confirmación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-142">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="0ea00-143">Volverá a su página **Automatizar la comprensión del contenido**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-143">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="0ea00-144">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="0ea00-144">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="0ea00-145">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="0ea00-145">Assign licenses</span></span>

<span data-ttu-id="0ea00-146">Una vez que haya configurado SharePoint Syntex, debe asignar licencias para los usuarios que utilizarán cualquier función de SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="0ea00-146">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="0ea00-147">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="0ea00-147">To assign licenses:</span></span>

1. <span data-ttu-id="0ea00-148">En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-148">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="0ea00-149">Seleccione los usuarios a los que desea conceder licencias y haga clic en **Administrar licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-149">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="0ea00-150">Seleccione **Asignar más**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-150">Select **Assign more**.</span></span>

4. <span data-ttu-id="0ea00-151">Seleccione **Intelligent Content Services**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-151">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="0ea00-152">En **Aplicaciones**, asegúrese de que estén seleccionados **Common Data Service** e **Intelligent Content Services**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-152">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="0ea00-154">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="0ea00-154">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="0ea00-155">Créditos de Generador de IA</span><span class="sxs-lookup"><span data-stu-id="0ea00-155">AI Builder credits</span></span>

<span data-ttu-id="0ea00-156">Si tiene 300 o más licencias de SharePoint Syntex en su organización, se le asignará un millón de créditos del Generador de IA.</span><span class="sxs-lookup"><span data-stu-id="0ea00-156">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="0ea00-157">Si tiene menos de 300 licencias, debe comprar créditos del Generador de IA para poder utilizar el procesamiento de formularios.</span><span class="sxs-lookup"><span data-stu-id="0ea00-157">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="0ea00-158">Puede estimar la capacidad del Generador de IA que lo hace adecuado para usted con la calculadora del [Generador de IA](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="0ea00-158">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="0ea00-159">Vaya al [Centro de administración de la Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar sus créditos y el uso.</span><span class="sxs-lookup"><span data-stu-id="0ea00-159">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ea00-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ea00-160">See also</span></span>

[<span data-ttu-id="0ea00-161">Visión general del modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="0ea00-161">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="0ea00-162">Paso a paso: cómo crear un modelo de comprensión de documentos (video)</span><span class="sxs-lookup"><span data-stu-id="0ea00-162">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

