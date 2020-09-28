---
title: Configurar SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Configurar la comprensión del contenido en Project Cortex
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294891"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="e9fc0-103">Configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="e9fc0-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="e9fc0-104">Los administradores pueden usar el centro de administración de Microsoft 365 para instalar y Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="e9fc0-105">Antes de empezar, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9fc0-105">Consider the following before you start:</span></span>

- <span data-ttu-id="e9fc0-106">¿Qué sitios de SharePoint habilitará el procesamiento de formularios?</span><span class="sxs-lookup"><span data-stu-id="e9fc0-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="e9fc0-107">Todos ellos, algunos o seleccione sitios?</span><span class="sxs-lookup"><span data-stu-id="e9fc0-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="e9fc0-108">¿Cuál será el nombre de su centro de contenido y quién es el administrador del sitio principal?</span><span class="sxs-lookup"><span data-stu-id="e9fc0-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="e9fc0-109">Puede cambiar la configuración después de la configuración inicial en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="e9fc0-110">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="e9fc0-111">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="e9fc0-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="e9fc0-112">Antes de la instalación, asegúrese de planear la mejor manera de configurar y configurar la comprensión del contenido en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="e9fc0-113">Por ejemplo, debe tener en cuenta los siguientes nombres de:</span><span class="sxs-lookup"><span data-stu-id="e9fc0-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="e9fc0-114">Los sitios de SharePoint en los que desea habilitar el procesamiento de formularios: todos, algunos o determinados sitios</span><span class="sxs-lookup"><span data-stu-id="e9fc0-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="e9fc0-115">El centro de contenido y el nombre del administrador del sitio principal</span><span class="sxs-lookup"><span data-stu-id="e9fc0-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="e9fc0-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9fc0-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="e9fc0-117">Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y configurar el conocimiento del contenido.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="e9fc0-118">Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la instalación y en todo el contenido que comprenda la configuración de administración en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="e9fc0-119">Para configurar SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="e9fc0-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="e9fc0-120">En el centro de administración de Microsoft 365, seleccione **instalación**y, a continuación, ver la sección de conocimientos de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="e9fc0-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="e9fc0-121">En la sección conocimientos de la **organización** , seleccione **automatizar el conocimiento del contenido**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Página de configuración de conocimientos de la organización](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="e9fc0-123">En la página **automatizar Syntex de SharePoint** , **haga clic en introducción para** recorrer el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Inicio de la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="e9fc0-125">En la página activar el etiquetado de imágenes, elija si quiere permitir el [etiquetado de imágenes](image-tagging.md).</span><span class="sxs-lookup"><span data-stu-id="e9fc0-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Captura de pantalla de las opciones de etiquetado de imágenes](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="e9fc0-127">En la página **configurar procesamiento de formularios** , puede elegir si desea permitir que los usuarios puedan usar el generador de AI para crear modelos de procesamiento de formularios en bibliotecas de documentos de SharePoint específicas.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="e9fc0-128">Una opción de menú estará disponible en la cinta de la biblioteca de documentos para **crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="e9fc0-129">Para **qué bibliotecas de SharePoint se debe mostrar la opción para crear un modelo de procesamiento de formularios**, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="e9fc0-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="e9fc0-130">**Todas las bibliotecas de SharePoint** para que estén disponibles para todas las bibliotecas de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="e9fc0-131">**Solo las bibliotecas de los sitios seleccionados**y, a continuación, seleccione los sitios en los que desea que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![Configurar el procesamiento de formularios](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="e9fc0-133">La habilitación de esta opción en una biblioteca de documentos de SharePoint no afecta a los modelos existentes aplicados a la biblioteca o a la capacidad de aplicar documentos que comprenden los modelos a una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="e9fc0-134">En la página **crear centro de contenido** , puede crear un sitio del centro de contenido de SharePoint en el que los usuarios puedan crear y administrar los modelos de comprensión de documentos.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="e9fc0-135">a.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-135">a.</span></span> <span data-ttu-id="e9fc0-136">En **nombre del sitio**, escriba el nombre que desea asignar al sitio del centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="e9fc0-137">b.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-137">b.</span></span> <span data-ttu-id="e9fc0-138">La **dirección del sitio** mostrará la dirección URL del sitio, en función de lo que haya seleccionado para el nombre del sitio.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="e9fc0-139">Si desea cambiarla, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-139">If you want to change it, click **Edit**.</span></span></br>

      ![Crear centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="e9fc0-141">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-141">Select **Next**.</span></span>

7. <span data-ttu-id="e9fc0-142">En la página **revisar y finalizar** , puede mirar la configuración seleccionada y elegir realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="e9fc0-143">Si está satisfecho con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="e9fc0-144">En la página Confirmación, haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="e9fc0-145">Volverá a la página de **comprensión automatizada del contenido** .</span><span class="sxs-lookup"><span data-stu-id="e9fc0-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="e9fc0-146">En esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="e9fc0-147">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="e9fc0-147">Assign licenses</span></span>

<span data-ttu-id="e9fc0-148">Una vez configurados los Syntex de SharePoint, debe asignar licencias para los usuarios que van a usar las características de procesamiento de formularios y de descripción de documentos.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="e9fc0-149">Para asignar licencias:</span><span class="sxs-lookup"><span data-stu-id="e9fc0-149">To assign licenses:</span></span>

1. <span data-ttu-id="e9fc0-150">En el centro de administración de Microsoft 365, en **usuarios**, haga clic en **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="e9fc0-151">Seleccione los usuarios a los que quiera conceder una licencia y haga clic en **administrar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="e9fc0-152">Seleccione **asignar más**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="e9fc0-153">Seleccione **servicios de contenido inteligente**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="e9fc0-154">En **aplicaciones**, asegúrese **de que servicio de datos común para servicios de contenido inteligente** y **servicios de contenido inteligente** están seleccionados.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Licencias de SharePoint Syntex en el centro de administración de Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="e9fc0-156">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="e9fc0-157">Créditos del generador de AI</span><span class="sxs-lookup"><span data-stu-id="e9fc0-157">AI Builder credits</span></span>

<span data-ttu-id="e9fc0-158">Si tiene 300 o más licencias de Syntex de SharePoint para SharePoint Syntex en su organización, se le asignarán 1 millón los créditos del generador de AI.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="e9fc0-159">Si tiene menos de 300 licencias, debe adquirir créditos del generador de AI para poder usar el procesamiento de formularios.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="e9fc0-160">Puede calcular la capacidad del generador de AI que más le conviene con la [calculadora del generador de AI](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="e9fc0-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

1. <span data-ttu-id="e9fc0-161">Vaya al centro de administración de la [plataforma de energía](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar los créditos y el uso.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9fc0-162">Habilitar esta opción en una biblioteca de documentos de SharePoint no afecta a los modelos existentes que se aplican a la biblioteca o a la capacidad de aplicar documentos que comprenden los modelos a una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-162">Enable this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
2. <span data-ttu-id="e9fc0-163">En la página **crear centro de contenido** , puede crear un sitio del centro de contenido de SharePoint para el que los usuarios puedan crear y administrar los modelos de comprensión de documentos.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-163">From the **Create Content Center** page, you can create a SharePoint content center site for which users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="e9fc0-164">a.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-164">a.</span></span> <span data-ttu-id="e9fc0-165">En **nombre del sitio**, escriba el nombre que desee para el sitio del centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-165">For **Site name**, type the name you want for the content center site.</span></span></br>
    <span data-ttu-id="e9fc0-166">b.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-166">b.</span></span> <span data-ttu-id="e9fc0-167">La **dirección del sitio** muestra la dirección URL del sitio, en función del nombre del sitio.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-167">The **Site address** shows the URL for your site, based on the site name.</span></span></br>

    > [!NOTE] 
    > <span data-ttu-id="e9fc0-168">Aunque puede seleccionar cualquier idioma admitido, los modelos de comprensión de contenido solo se pueden crear para inglés.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-168">While you can select any supported language, content understanding models can only be created for English.</span></span></br>

      ![Crear centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>

3. <span data-ttu-id="e9fc0-170">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-170">Select **Next**.</span></span>

4. <span data-ttu-id="e9fc0-171">En la página **finalizar y revisar** , mire la configuración seleccionada y elija realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-171">On the **Finish and review** page, look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="e9fc0-172">Si está satisfecho con las selecciones, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-172">If you are satisfied with your selections, select **Activate**.</span></span>

5. <span data-ttu-id="e9fc0-173">Se muestra el **contenido que comprende** la página activada, confirmando que el sistema agregó sus preferencias de procesamiento de formulario y creó el sitio del centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-173">The **Content understanding activated** page displays, confirming the system added your form processing preferences and created the Content Center site.</span></span> <span data-ttu-id="e9fc0-174">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-174">Select **Done**.</span></span>

6. <span data-ttu-id="e9fc0-175">Volverá a la página de **comprensión automatizada del contenido** .</span><span class="sxs-lookup"><span data-stu-id="e9fc0-175">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="e9fc0-176">En esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-176">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e9fc0-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9fc0-177">See also</span></span>

[<span data-ttu-id="e9fc0-178">Información general sobre el modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="e9fc0-178">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="e9fc0-179">Paso a paso: Cómo crear un documento que comprenda el modelo (vídeo)</span><span class="sxs-lookup"><span data-stu-id="e9fc0-179">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

