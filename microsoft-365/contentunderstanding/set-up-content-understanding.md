---
title: Configurar SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Establecer la comprensión del contenido en el Project Cortex.
ms.openlocfilehash: a9713f1d28cf863ab827d2975e84042026105b3f
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976393"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="b57c8-103">Configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b57c8-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="b57c8-104">Los administradores pueden usar el Centro de administración de Microsoft 365 para configurar [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="b57c8-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="b57c8-105">Considere lo siguiente antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="b57c8-105">Consider the following before you start:</span></span>

- <span data-ttu-id="b57c8-106">¿En qué sitios de SharePoint se va a habilitar el procesamiento de formularios?</span><span class="sxs-lookup"><span data-stu-id="b57c8-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="b57c8-107">¿Todos ellos, algunos, o seleccionar sitios?</span><span class="sxs-lookup"><span data-stu-id="b57c8-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="b57c8-108">¿Qué nombre le pondrá a su centro de contenido de forma predeterminada?</span><span class="sxs-lookup"><span data-stu-id="b57c8-108">What will you name your default content center?</span></span>

<span data-ttu-id="b57c8-109">Puede cambiar su configuración después de la configuración inicial en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b57c8-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b57c8-110">Antes de la configuración, asegúrese de planificar la mejor manera de configurar la comprensión del contenido en su entorno.</span><span class="sxs-lookup"><span data-stu-id="b57c8-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="b57c8-111">Por ejemplo, hay que tomar las siguientes decisiones:</span><span class="sxs-lookup"><span data-stu-id="b57c8-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="b57c8-112">Los sitios de SharePoint en los que desea habilitar el procesamiento de formularios: todos, algunos o sitios seleccionados</span><span class="sxs-lookup"><span data-stu-id="b57c8-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="b57c8-113">El nombre y los administradores de su centro de contenido</span><span class="sxs-lookup"><span data-stu-id="b57c8-113">The name and admins or your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="b57c8-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="b57c8-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="b57c8-115">Debe tener permisos de administrador global o de administrador de SharePoint para poder acceder al Centro de administración de Microsoft 365 y configurar la comprensión del contenido.</span><span class="sxs-lookup"><span data-stu-id="b57c8-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="b57c8-116">Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la configuración, y a lo largo de la comprensión del contenido de la configuración de administración en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b57c8-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="b57c8-117">Para configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b57c8-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="b57c8-118">En el Centro de administración de Microsoft 365, seleccione **Configuración** y luego vea la sección **Archivos y contenido**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="b57c8-119">En la sección **Archivos y contenido**, seleccione **Automatizar la comprensión del contenido**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="b57c8-120">En la página para **Automatizar la comprensión del contenido**, haga clic en **Introducción** para recorrer el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="b57c8-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b57c8-121">![Iniciar la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="b57c8-121">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="b57c8-122">En la página **Configurar el procesamiento** de formularios, puede elegir si desea que los usuarios puedan crear modelos de procesamiento de formularios en bibliotecas de documentos específicos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b57c8-122">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="b57c8-123">En la cinta de opciones de la biblioteca de documentos estará disponible una opción de menú para **Crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="b57c8-123">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="b57c8-124">Para **Qué bibliotecas de SharePoint debe mostrar la opción de crear un modelo de procesamiento de formularios**, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="b57c8-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="b57c8-125">**Bibliotecas en todos los sitios de SharePoint** para que esté disponible en todas las bibliotecas de SharePoint de su organización.</span><span class="sxs-lookup"><span data-stu-id="b57c8-125">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="b57c8-126">**Bibliotecas en los sitios de SharePoint seleccionados**, y a luego, seleccione los sitios en los que desea que esté disponible o cargue una lista de hasta 50 sitios.</span><span class="sxs-lookup"><span data-stu-id="b57c8-126">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="b57c8-127">**No hay bibliotecas de SharePoint** si no quiere que esté disponible para ningún sitio (puede cambiar esto después de la configuración).</span><span class="sxs-lookup"><span data-stu-id="b57c8-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b57c8-128">![Configurar el procesamiento del formulario](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="b57c8-128">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="b57c8-129">Quitando un sitio después de incluirlo no afecta a los modelos existentes aplicados a las bibliotecas de ese sitio ni a la capacidad de aplicar modelos de comprensión de documentos a una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b57c8-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="b57c8-130">En la página **Crear centro de contenido**, puede crear un sitio de centro de contenido de SharePoint en el que sus usuarios puedan crear y administrar modelos de comprensión de documentos.</span><span class="sxs-lookup"><span data-stu-id="b57c8-130">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="b57c8-131">Para el **Nombre del sitio**, escriba el nombre que quiere darle a su sitio de centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="b57c8-131">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="b57c8-132">La **Dirección del sitio** mostrará el URL de su sitio, basado en lo que usted seleccionó para el nombre del sitio.</span><span class="sxs-lookup"><span data-stu-id="b57c8-132">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="b57c8-133">Si desea cambiar la configuración, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-133">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="b57c8-134">![Crear el centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="b57c8-134">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="b57c8-135">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-135">Select **Next**.</span></span>

6. <span data-ttu-id="b57c8-136">En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="b57c8-136">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b57c8-137">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-137">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="b57c8-138">En la página de confirmación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-138">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="b57c8-139">Volverá a su página **Automatizar la comprensión del contenido**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-139">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="b57c8-140">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="b57c8-140">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="b57c8-141">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="b57c8-141">Assign licenses</span></span>

<span data-ttu-id="b57c8-142">Una vez que haya configurado SharePoint Syntex, debe asignar licencias para los usuarios que utilizarán cualquier función de SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="b57c8-142">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="b57c8-143">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="b57c8-143">To assign licenses:</span></span>

1. <span data-ttu-id="b57c8-144">En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-144">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="b57c8-145">Seleccione los usuarios a los que desea conceder licencias y haga clic en **Administrar licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-145">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="b57c8-146">Seleccione **Asignar más**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-146">Select **Assign more**.</span></span>

4. <span data-ttu-id="b57c8-147">Seleccione **SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-147">Select **SharePoint Syntex**.</span></span> <span data-ttu-id="b57c8-148">En **Aplicaciones**, asegúrese de estén seleccionadas las opciones **Servicio de datos común para SharePoint Syntex**, **SharePoint Syntex** y **SharePoint Syntex: tipo SPO**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-148">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b57c8-149">![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="b57c8-149">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="b57c8-150">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="b57c8-150">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="b57c8-151">Créditos de Generador de IA</span><span class="sxs-lookup"><span data-stu-id="b57c8-151">AI Builder credits</span></span>

<span data-ttu-id="b57c8-152">Si tiene 300 o más licencias de SharePoint Syntex en su organización, se le asignará un millón de créditos del Generador de IA.</span><span class="sxs-lookup"><span data-stu-id="b57c8-152">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="b57c8-153">Si tiene menos de 300 licencias, debe comprar créditos del Generador de IA para poder utilizar el procesamiento de formularios.</span><span class="sxs-lookup"><span data-stu-id="b57c8-153">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="b57c8-154">Puede estimar la capacidad del Generador de IA que lo hace adecuado para usted con la calculadora del [Generador de IA](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="b57c8-154">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="b57c8-155">Vaya al [Centro de administración de la Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar sus créditos y el uso.</span><span class="sxs-lookup"><span data-stu-id="b57c8-155">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b57c8-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b57c8-156">See also</span></span>

[<span data-ttu-id="b57c8-157">Visión general del modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="b57c8-157">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="b57c8-158">Paso a paso: cómo crear un modelo de comprensión de documentos (video)</span><span class="sxs-lookup"><span data-stu-id="b57c8-158">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)
