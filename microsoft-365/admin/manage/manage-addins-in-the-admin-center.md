---
title: Administrar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: d678755b28daea1578ce2a5d2e387492cf32d368
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636063"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="ac3e7-103">Administrar complementos en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="ac3e7-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="ac3e7-104">Office complementos le ayudarán a personalizar los documentos y simplificar la forma en que tiene acceso a la información en la web (vea Empezar a usar el complemento [Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)web ).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="ac3e7-105">Después de que un administrador implemente complementos para los usuarios de una organización, el administrador puede desactivar o activar los complementos, editar, eliminar y administrar el acceso a los complementos.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="ac3e7-106">Para obtener más información acerca de la instalación de complementos desde el Centro de administración, vea [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="ac3e7-107">Estados del complemento</span><span class="sxs-lookup"><span data-stu-id="ac3e7-107">Add-in states</span></span>

<span data-ttu-id="ac3e7-108">Un complemento puede estar en el **estado On** o **Off.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="ac3e7-109">Estado</span><span class="sxs-lookup"><span data-stu-id="ac3e7-109">State</span></span> | <span data-ttu-id="ac3e7-110">Cómo se produce el estado</span><span class="sxs-lookup"><span data-stu-id="ac3e7-110">How the state occurs</span></span> | <span data-ttu-id="ac3e7-111">Impacto</span><span class="sxs-lookup"><span data-stu-id="ac3e7-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="ac3e7-112">**Activo**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-112">**Active**</span></span>  <br/> |<span data-ttu-id="ac3e7-113">El administrador carizó el complemento y lo asignó a usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="ac3e7-114">Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="ac3e7-115">**Desactivado**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="ac3e7-116">El administrador ha desactivado el complemento.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="ac3e7-117">Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="ac3e7-118">Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="ac3e7-119">**Eliminado**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="ac3e7-120">El administrador ha eliminado el complemento.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="ac3e7-121">Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="ac3e7-122">Considere la posibilidad de eliminar un complemento si ya nadie lo está usando.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="ac3e7-123">Por ejemplo, desactivar un complemento puede tener sentido si un complemento se usa solo durante determinadas horas del año.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="ac3e7-124">Eliminar un complemento</span><span class="sxs-lookup"><span data-stu-id="ac3e7-124">Delete an add-in</span></span>

<span data-ttu-id="ac3e7-125">También puede eliminar un complemento que se implementó.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="ac3e7-126">En el Centro de administración, vaya a la **página Configuración** servicios  >  **& complementos.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac3e7-127">El Centro de administración se actualiza a la experiencia de implementación con aplicaciones integradas.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="ac3e7-128">Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a Configuración  >  **aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="ac3e7-129">En la parte superior de la página Aplicaciones **integradas,** elija Complementos . </span><span class="sxs-lookup"><span data-stu-id="ac3e7-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="ac3e7-130">Seleccione el complemento implementado.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="ac3e7-131">Haga clic **en Eliminar complemento**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="ac3e7-132">Quite el botón Complemento de la esquina inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="ac3e7-133">Valide su selección y elija **Quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="ac3e7-134">Editar el acceso del complemento</span><span class="sxs-lookup"><span data-stu-id="ac3e7-134">Edit add-in access</span></span>

<span data-ttu-id="ac3e7-135">Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="ac3e7-136">En el Centro de administración, vaya a la **página Configuración** servicios  >  **& complementos.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac3e7-137">El Centro de administración se actualiza a la experiencia de implementación con aplicaciones integradas.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="ac3e7-138">Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a Configuración  >  **aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="ac3e7-139">En la parte superior de la página Aplicaciones **integradas,** elija Complementos . </span><span class="sxs-lookup"><span data-stu-id="ac3e7-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="ac3e7-140">Seleccione el complemento implementado.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="ac3e7-141">Haga clic **en Editar** en Quién **tiene Access**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="ac3e7-142">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="ac3e7-143">Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="ac3e7-144">Outlook instalación del complemento se administra mediante un [proceso diferente.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="ac3e7-145">Como organización, es posible que quieras impedir la descarga de nuevos Office complementos de la Office Store.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="ac3e7-146">Esto se puede usar junto con la implementación centralizada para garantizar que solo los complementos aprobados por la organización se implementen en los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="ac3e7-147">**Para desactivar la adquisición de complementos**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="ac3e7-148">En el centro de administración, vaya a la página **Configuración** \>[de servicios &amp;complementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac3e7-149">El Centro de administración se actualiza a la experiencia de implementación con aplicaciones integradas.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="ac3e7-150">Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a Configuración  >  **aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="ac3e7-151">En la parte superior de la página Aplicaciones **integradas,** elija Complementos . </span><span class="sxs-lookup"><span data-stu-id="ac3e7-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="ac3e7-152">Seleccione **Aplicaciones y servicios que pertenecen al usuario**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="ac3e7-153">Desactive la opción para permitir que los usuarios accedan a la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="ac3e7-154">Esto impedirá que todos los usuarios adquieran los siguientes complementos de la tienda.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="ac3e7-155">Complementos para Word, Excel y PowerPoint 2016 desde:</span><span class="sxs-lookup"><span data-stu-id="ac3e7-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="ac3e7-156">Windows</span><span class="sxs-lookup"><span data-stu-id="ac3e7-156">Windows</span></span>
      - <span data-ttu-id="ac3e7-157">Mac</span><span class="sxs-lookup"><span data-stu-id="ac3e7-157">Mac</span></span>
      - <span data-ttu-id="ac3e7-158">Office</span><span class="sxs-lookup"><span data-stu-id="ac3e7-158">Office</span></span>
        
        
    - <span data-ttu-id="ac3e7-159">Adquisiciones a partir de **AppSource**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="ac3e7-160">Complementos dentro de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac3e7-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="ac3e7-161">Un usuario que intente acceder a la tienda verá el siguiente mensaje: Lo sentimos, Microsoft 365 se ha configurado para impedir la adquisición individual de Office complementos de la **Tienda.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="ac3e7-162">La compatibilidad para desactivar la tienda Office está disponible en las siguientes versiones:</span><span class="sxs-lookup"><span data-stu-id="ac3e7-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="ac3e7-163">Windows: 16.0.9001: Actualmente disponible.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="ac3e7-164">Mac: 16.10.18011401- Actualmente disponible.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="ac3e7-165">iOS: 2.9.18010804: disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="ac3e7-166">La web: disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-166">The web - Currently available.</span></span>
    
<span data-ttu-id="ac3e7-167">Esto no impide que un administrador use la implementación centralizada para asignar un complemento desde Office Store.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="ac3e7-168">Para evitar que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para usar solo la cuenta de la organización.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="ac3e7-169">Para obtener más información, vea [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="ac3e7-170">Impedir que los usuarios accedan a la tienda de office también impedirá que puedan realizar la instalación Office complementos para realizar [pruebas desde un recurso compartido de red.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="ac3e7-171">Más información sobre la experiencia del usuario final con complementos</span><span class="sxs-lookup"><span data-stu-id="ac3e7-171">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="ac3e7-172">Después de implementar un complemento, los usuarios finales pueden empezar a usarlo en sus aplicaciones de Office (vea [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="ac3e7-173">El complemento aparece en todas las plataformas compatibles con el complemento.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="ac3e7-p109">Si el complemento es compatible con comandos de complemento, estos aparecerán en la cinta de opciones de Office. En el siguiente ejemplo, el comando **Buscar cita** aparece para el complemento **Citas**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-p109">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office cinta de opciones con citas de búsqueda](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="ac3e7-177">Si el complemento implementado no admite comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través de **Mis complementos**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="ac3e7-178">En Word 2016, Excel 2016 o PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="ac3e7-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="ac3e7-179">Seleccione **Insertar \> mis complementos**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="ac3e7-180">Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="ac3e7-181">Haga doble clic en el complemento que implementó anteriormente (en este ejemplo, **Citations**).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-181">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![Pestaña Administración administrada de la Office complementos](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="ac3e7-183">En Outlook</span><span class="sxs-lookup"><span data-stu-id="ac3e7-183">In Outlook</span></span>

1. <span data-ttu-id="ac3e7-184">En la **cinta de** opciones Inicio, seleccione **Obtener complementos**.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-184">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Botón Tienda en Outlook](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="ac3e7-186">Seleccione **Gestionado por el administrador** en la barra de navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="ac3e7-187">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="ac3e7-187">Related content</span></span>

<span data-ttu-id="ac3e7-188">[Implementar complementos en el Centro](./manage-deployment-of-add-ins.md) de administración (artículo)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-188">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="ac3e7-189">Obtenga más información sobre cómo crear [y crear Office complementos](/office/dev/add-ins/overview/office-add-ins) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="ac3e7-190">[Usar cmdlets de PowerShell de implementación centralizada para administrar complementos](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="ac3e7-191">[Solución de problemas: el usuario no ve complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-191">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="ac3e7-192">[Menores y la adquisición de complementos](./minors-and-acquiring-addins-from-the-store.md) de la Microsoft Store (artículo)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-192">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>