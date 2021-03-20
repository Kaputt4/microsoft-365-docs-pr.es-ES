---
title: Administrar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Obtenga información sobre el uso de complementos centralizados para implementar complementos para usuarios y grupos de la organización.
ms.openlocfilehash: 0750b6c9b91bc5cbd67d227fadb304bfc6cf7537
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915403"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="7b5bb-103">Administrar complementos en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="7b5bb-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7b5bb-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-104">The admin center is changing.</span></span> <span data-ttu-id="7b5bb-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="7b5bb-106">Los complementos de Office le ayudan a personalizar los documentos y a simplificar la forma en que accede a la información en la web (vea [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="7b5bb-107">Después de que un administrador implemente complementos para los usuarios de una organización, el administrador puede desactivar o activar los complementos, editar, eliminar y administrar el acceso a los complementos.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="7b5bb-108">Para obtener más información acerca de la instalación de complementos desde el Centro de administración, vea [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="7b5bb-109">Estados del complemento</span><span class="sxs-lookup"><span data-stu-id="7b5bb-109">Add-in states</span></span>

<span data-ttu-id="7b5bb-110">Un complemento puede estar en el **estado On** o **Off.**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="7b5bb-111">**Estado**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-111">**State**</span></span>|<span data-ttu-id="7b5bb-112">**Cómo se produce el estado**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-112">**How the state occurs**</span></span>|<span data-ttu-id="7b5bb-113">**Impacto**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7b5bb-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-114">**Active**</span></span>  <br/> |<span data-ttu-id="7b5bb-115">El administrador carizó el complemento y lo asignó a usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="7b5bb-116">Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="7b5bb-117">**Desactivado**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="7b5bb-118">El administrador ha desactivado el complemento.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="7b5bb-119">Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="7b5bb-120">Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="7b5bb-121">**Eliminado**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="7b5bb-122">El administrador ha eliminado el complemento.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="7b5bb-123">Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="7b5bb-124">Considere la posibilidad de eliminar un complemento si ya nadie lo está usando.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="7b5bb-125">Por ejemplo, desactivar un complemento puede tener sentido si un complemento se usa solo durante determinadas horas del año.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="7b5bb-126">Eliminar un complemento</span><span class="sxs-lookup"><span data-stu-id="7b5bb-126">Delete an add-in</span></span>

<span data-ttu-id="7b5bb-127">También puede eliminar un complemento que se implementó.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="7b5bb-128">En el Centro de administración, vaya a la página **Servicios**  >  **& configuración.**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="7b5bb-129">El Centro de administración se actualiza a la experiencia de implementación con aplicaciones integradas.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="7b5bb-130">Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a **Configuración**  >  **aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="7b5bb-131">En la parte superior de la página Aplicaciones **integradas,** elija Complementos . </span><span class="sxs-lookup"><span data-stu-id="7b5bb-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="7b5bb-132">Seleccione el complemento implementado.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="7b5bb-133">Haga clic **en Eliminar complemento**.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="7b5bb-134">Quite el botón Complemento de la esquina inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="7b5bb-135">Valide las selecciones y elija **Quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="7b5bb-136">Editar acceso a complementos</span><span class="sxs-lookup"><span data-stu-id="7b5bb-136">Edit add-in access</span></span>

<span data-ttu-id="7b5bb-137">Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="7b5bb-138">En el Centro de administración, vaya a la página **Servicios**  >  **& configuración.**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="7b5bb-139">El Centro de administración se actualiza a la experiencia de implementación con aplicaciones integradas.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="7b5bb-140">Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a **Configuración**  >  **aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="7b5bb-141">En la parte superior de la página Aplicaciones **integradas,** elija Complementos . </span><span class="sxs-lookup"><span data-stu-id="7b5bb-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="7b5bb-142">Seleccione el complemento implementado.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="7b5bb-143">Haga clic **en Editar** en Quién **tiene Access**.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="7b5bb-144">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="7b5bb-145">Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)</span><span class="sxs-lookup"><span data-stu-id="7b5bb-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="7b5bb-146">La instalación del complemento de Outlook se administra mediante un [proceso diferente.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="7b5bb-146">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="7b5bb-147">Como organización, es posible que desee impedir la descarga de nuevos complementos de Office desde la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="7b5bb-148">Esto se puede usar junto con la implementación centralizada para garantizar que solo los complementos aprobados por la organización se implementen en los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="7b5bb-149">**Para desactivar la adquisición de complementos**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="7b5bb-150">En el centro de administración, vaya a la página **Configuración** \>[de servicios &amp;complementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="7b5bb-151">El Centro de administración se actualiza a la experiencia de implementación con aplicaciones integradas.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="7b5bb-152">Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a **Configuración**  >  **aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="7b5bb-153">En la parte superior de la página Aplicaciones **integradas,** elija Complementos . </span><span class="sxs-lookup"><span data-stu-id="7b5bb-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="7b5bb-154">Seleccione **Aplicaciones y servicios de propiedad del usuario.**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="7b5bb-155">Desactive la opción para permitir que los usuarios accedan al almacén de Office.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="7b5bb-156">Esto impedirá que todos los usuarios adquieran los siguientes complementos de la tienda.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="7b5bb-157">Complementos para Word, Excel y PowerPoint 2016 desde:</span><span class="sxs-lookup"><span data-stu-id="7b5bb-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="7b5bb-158">Windows</span><span class="sxs-lookup"><span data-stu-id="7b5bb-158">Windows</span></span>
    
  - <span data-ttu-id="7b5bb-159">Mac</span><span class="sxs-lookup"><span data-stu-id="7b5bb-159">Mac</span></span>
    
  - <span data-ttu-id="7b5bb-160">Office</span><span class="sxs-lookup"><span data-stu-id="7b5bb-160">Office</span></span>
    
    
- <span data-ttu-id="7b5bb-161">Adquisiciones a partir de **AppSource**</span><span class="sxs-lookup"><span data-stu-id="7b5bb-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="7b5bb-162">Complementos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b5bb-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="7b5bb-163">Un usuario que intente acceder a la tienda verá el siguiente mensaje: Lo **sentimos, Microsoft 365** se ha configurado para impedir la adquisición individual de complementos de la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="7b5bb-164">La compatibilidad para desactivar la Tienda Office está disponible en las siguientes versiones:</span><span class="sxs-lookup"><span data-stu-id="7b5bb-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="7b5bb-165">Windows: 16.0.9001: disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="7b5bb-166">Mac: 16.10.18011401- Actualmente disponible.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="7b5bb-167">iOS: 2.9.18010804: disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="7b5bb-168">La web: disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-168">The web - Currently available.</span></span>
    
<span data-ttu-id="7b5bb-169">Esto no impide que un administrador use la implementación centralizada para asignar un complemento desde la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="7b5bb-170">Para evitar que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para usar solo la cuenta de la organización.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="7b5bb-171">Para obtener más información, vea [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-171">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="7b5bb-172">Impedir que los usuarios accedan a la tienda de office también impedirá que puedan realizar la instalación local de [complementos de Office para realizar pruebas.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="7b5bb-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="7b5bb-173">Más información sobre la experiencia del usuario final con complementos</span><span class="sxs-lookup"><span data-stu-id="7b5bb-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="7b5bb-174">Después de implementar un complemento, los usuarios finales pueden empezar a usarlo en sus aplicaciones de Office (vea [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="7b5bb-175">El complemento aparece en todas las plataformas compatibles con el complemento.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="7b5bb-p110">Si el complemento es compatible con comandos de complemento, estos aparecerán en la cinta de opciones de Office. En el siguiente ejemplo, el comando **Buscar cita** aparece para el complemento **Citas**.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Cinta de Office con citas de búsqueda](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="7b5bb-179">Si el complemento implementado no admite comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través de **Mis complementos**.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="7b5bb-180">En Word 2016, Excel 2016 o PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="7b5bb-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="7b5bb-181">Seleccione **Insertar \> mis complementos**.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="7b5bb-182">Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="7b5bb-183">Haga doble clic en el complemento que ha implementado antes (en este ejemplo, **Citas** ).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="7b5bb-184">![Pestaña Administración administrada de la página Complementos de Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="7b5bb-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="7b5bb-185">En Outlook</span><span class="sxs-lookup"><span data-stu-id="7b5bb-185">In Outlook</span></span>

1. <span data-ttu-id="7b5bb-186">En la **cinta de** opciones Inicio, seleccione **Obtener complementos**.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="7b5bb-187">![Botón Tienda en Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="7b5bb-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="7b5bb-188">Seleccione **Administrado por el administrador** en la navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="7b5bb-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="7b5bb-189">Más información</span><span class="sxs-lookup"><span data-stu-id="7b5bb-189">Learn more</span></span>

[<span data-ttu-id="7b5bb-190">Implementar complementos en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="7b5bb-190">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="7b5bb-191">Obtenga más información sobre la creación y generación de [complementos de Office](/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="7b5bb-191">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="7b5bb-192">[Use cmdlets de PowerShell de implementación centralizada para administrar complementos.](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="7b5bb-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="7b5bb-193">Solución de problemas: el usuario no ve complementos</span><span class="sxs-lookup"><span data-stu-id="7b5bb-193">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="7b5bb-194">Menores y adquirir complementos de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="7b5bb-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)