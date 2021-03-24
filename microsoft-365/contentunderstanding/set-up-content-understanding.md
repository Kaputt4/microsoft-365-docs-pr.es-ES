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
ms.openlocfilehash: cc6fbfbfc130cc6e64b5d7c30e0a9db5f39036ac
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051572"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="576c1-103">Configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="576c1-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="576c1-104">Los administradores pueden usar el Centro de administración de Microsoft 365 para configurar [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="576c1-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="576c1-105">Considere lo siguiente antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="576c1-105">Consider the following before you start:</span></span>

- <span data-ttu-id="576c1-106">¿En qué sitios de SharePoint se va a habilitar el procesamiento de formularios?</span><span class="sxs-lookup"><span data-stu-id="576c1-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="576c1-107">¿Todos ellos, algunos, o seleccionar sitios?</span><span class="sxs-lookup"><span data-stu-id="576c1-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="576c1-108">¿Qué nombre le pondrá a su centro de contenido de forma predeterminada?</span><span class="sxs-lookup"><span data-stu-id="576c1-108">What will you name your default content center?</span></span>

<span data-ttu-id="576c1-109">Puede cambiar su configuración después de la configuración inicial en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="576c1-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="576c1-110">Antes de la configuración, asegúrese de planificar la mejor manera de configurar la comprensión del contenido en su entorno.</span><span class="sxs-lookup"><span data-stu-id="576c1-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="576c1-111">Por ejemplo, hay que tomar las siguientes decisiones:</span><span class="sxs-lookup"><span data-stu-id="576c1-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="576c1-112">Los sitios de SharePoint en los que desea habilitar el procesamiento de formularios: todos, algunos o sitios seleccionados</span><span class="sxs-lookup"><span data-stu-id="576c1-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="576c1-113">El nombre y los administradores de su centro de contenido</span><span class="sxs-lookup"><span data-stu-id="576c1-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="576c1-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="576c1-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="576c1-115">Debe tener permisos de administrador global o de administrador de SharePoint para poder acceder al centro de administración de Microsoft 365 y configurar SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="576c1-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="576c1-116">Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la configuración, y a lo largo de la comprensión del contenido de la configuración de administración en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="576c1-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="576c1-117">Licencias</span><span class="sxs-lookup"><span data-stu-id="576c1-117">Licensing</span></span>

<span data-ttu-id="576c1-118">Para usar SharePoint Syntex, su organización debe tener una suscripción a SharePoint Syntex y cada usuario debe tener asignadas las siguientes licencias:</span><span class="sxs-lookup"><span data-stu-id="576c1-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="576c1-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="576c1-119">SharePoint Syntex</span></span>
- <span data-ttu-id="576c1-120">SharePoint Syntex: tipo SPO</span><span class="sxs-lookup"><span data-stu-id="576c1-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="576c1-121">Servicio de datos comunes para SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="576c1-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="576c1-122">Si cancela su suscripción a SharePoint Syntex (o la versión de prueba expira), los usuarios ya no podrán crear ni ejecutar modelos de procesamiento de formularios o comprensión de documentos y la plantilla del centro de contenido ya no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="576c1-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="576c1-123">Además, los informes de almacén de términos, la importación de taxonomía SKOS y la inserción de tipo de contenido ya no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="576c1-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="576c1-124">No se eliminará ningún contenido ni se modificarán los permisos del sitio.</span><span class="sxs-lookup"><span data-stu-id="576c1-124">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="576c1-125">Créditos de Generador de IA</span><span class="sxs-lookup"><span data-stu-id="576c1-125">AI Builder credits</span></span>

<span data-ttu-id="576c1-126">Si tiene 300 o más licencias de SharePoint Syntex en su organización, se le asignará un millón de créditos del Generador de IA.</span><span class="sxs-lookup"><span data-stu-id="576c1-126">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="576c1-127">Si tiene menos de 300 licencias, debe comprar créditos del Generador de IA para poder utilizar el procesamiento de formularios.</span><span class="sxs-lookup"><span data-stu-id="576c1-127">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="576c1-128">Puede estimar la capacidad del Generador de IA que lo hace adecuado para usted con la calculadora del [Generador de IA](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="576c1-128">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="576c1-129">Vaya al [Centro de administración de la Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar sus créditos y el uso.</span><span class="sxs-lookup"><span data-stu-id="576c1-129">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="576c1-130">Para configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="576c1-130">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="576c1-131">En el Centro de administración de Microsoft 365, seleccione **Configuración** y luego vea la sección **Archivos y contenido**.</span><span class="sxs-lookup"><span data-stu-id="576c1-131">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="576c1-132">En la sección **Archivos y contenido**, seleccione **Automatizar la comprensión del contenido**.</span><span class="sxs-lookup"><span data-stu-id="576c1-132">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="576c1-133">En la página para **Automatizar la comprensión del contenido**, haga clic en **Introducción** para recorrer el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="576c1-133">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="576c1-134">![Iniciar la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="576c1-134">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="576c1-135">En la página **Configurar el procesamiento** de formularios, puede elegir si desea que los usuarios puedan crear modelos de procesamiento de formularios en bibliotecas de documentos específicos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="576c1-135">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="576c1-136">En la cinta de opciones de la biblioteca de documentos estará disponible una opción de menú para **Crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="576c1-136">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="576c1-137">Para **Qué bibliotecas de SharePoint debe mostrar la opción de crear un modelo de procesamiento de formularios**, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="576c1-137">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="576c1-138">**Bibliotecas en todos los sitios de SharePoint** para que esté disponible en todas las bibliotecas de SharePoint de su organización.</span><span class="sxs-lookup"><span data-stu-id="576c1-138">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="576c1-139">**Bibliotecas en los sitios de SharePoint seleccionados**, y a luego, seleccione los sitios en los que desea que esté disponible o cargue una lista de hasta 50 sitios.</span><span class="sxs-lookup"><span data-stu-id="576c1-139">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="576c1-140">**No hay bibliotecas de SharePoint** si no quiere que esté disponible para ningún sitio (puede cambiar esto después de la configuración).</span><span class="sxs-lookup"><span data-stu-id="576c1-140">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="576c1-141">![Configurar el procesamiento del formulario](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="576c1-141">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="576c1-142">Quitando un sitio después de incluirlo no afecta a los modelos existentes aplicados a las bibliotecas de ese sitio ni a la capacidad de aplicar modelos de comprensión de documentos a una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="576c1-142">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="576c1-143">En la página **Crear centro de contenido**, puede crear un sitio de centro de contenido de SharePoint en el que sus usuarios puedan crear y administrar modelos de comprensión de documentos.</span><span class="sxs-lookup"><span data-stu-id="576c1-143">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="576c1-144">Para el **Nombre del sitio**, escriba el nombre que quiere darle a su sitio de centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="576c1-144">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="576c1-145">La **Dirección del sitio** mostrará el URL de su sitio, basado en lo que usted seleccionó para el nombre del sitio.</span><span class="sxs-lookup"><span data-stu-id="576c1-145">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="576c1-146">Si desea cambiar la configuración, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="576c1-146">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="576c1-147">![Crear el centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="576c1-147">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="576c1-148">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="576c1-148">Select **Next**.</span></span>

6. <span data-ttu-id="576c1-149">En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="576c1-149">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="576c1-150">Si está de acuerdo con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="576c1-150">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="576c1-151">En la página de confirmación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="576c1-151">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="576c1-152">Volverá a su página **Automatizar la comprensión del contenido**.</span><span class="sxs-lookup"><span data-stu-id="576c1-152">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="576c1-153">Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="576c1-153">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="576c1-154">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="576c1-154">Assign licenses</span></span>

<span data-ttu-id="576c1-155">Una vez que haya configurado SharePoint Syntex, debe asignar licencias para los usuarios que utilizarán cualquier función de SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="576c1-155">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="576c1-156">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="576c1-156">To assign licenses:</span></span>

1. <span data-ttu-id="576c1-157">En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="576c1-157">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="576c1-158">Seleccione los usuarios a los que quiere conceder licencias y haga clic en **Administrar licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="576c1-158">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="576c1-159">Elija **Aplicaciones** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="576c1-159">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="576c1-160">Seleccione **Mostrar aplicaciones para SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="576c1-160">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="576c1-161">En **Aplicaciones**, asegúrese de estén seleccionadas las opciones **Servicio de datos común para SharePoint Syntex**, **SharePoint Syntex** y **SharePoint Syntex: tipo SPO**.</span><span class="sxs-lookup"><span data-stu-id="576c1-161">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="576c1-162">![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="576c1-162">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="576c1-163">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="576c1-163">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="576c1-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="576c1-164">See also</span></span>

[<span data-ttu-id="576c1-165">Visión general del modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="576c1-165">Overview of the form processing model</span></span>](/ai-builder/form-processing-model-overview)

[<span data-ttu-id="576c1-166">Paso a paso: cómo crear un modelo de comprensión de documentos (video)</span><span class="sxs-lookup"><span data-stu-id="576c1-166">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)
