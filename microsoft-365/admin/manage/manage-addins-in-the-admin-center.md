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
description: Obtenga información sobre cómo usar los complementos centralizados para implementar complementos para los usuarios y grupos de su organización.
ms.openlocfilehash: c7f8b7bf71dbdaaf1c850c801a5145d3ab47a65c
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171297"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="88fa1-103">Administrar complementos en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="88fa1-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="88fa1-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="88fa1-104">The admin center is changing.</span></span> <span data-ttu-id="88fa1-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="88fa1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="88fa1-106">Los complementos de Office ayudan a personalizar los documentos y simplificar la forma de obtener acceso a la información en la web (vea [empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="88fa1-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="88fa1-107">Una vez que un administrador implementa complementos para los usuarios de una organización, el administrador puede activar o desactivar el complemento, editar, eliminar y administrar el acceso a los complementos.</span><span class="sxs-lookup"><span data-stu-id="88fa1-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="88fa1-108">Para obtener más información acerca de la instalación de complementos desde el centro de administración, consulte [deploy Add-Ins in the admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="88fa1-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="88fa1-109">Estados del complemento</span><span class="sxs-lookup"><span data-stu-id="88fa1-109">Add-in states</span></span>

<span data-ttu-id="88fa1-110">Un complemento puede estar en el estado **activado** o **desactivado** .</span><span class="sxs-lookup"><span data-stu-id="88fa1-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="88fa1-111">**Estado**</span><span class="sxs-lookup"><span data-stu-id="88fa1-111">**State**</span></span>|<span data-ttu-id="88fa1-112">**Cómo se produce el estado**</span><span class="sxs-lookup"><span data-stu-id="88fa1-112">**How the state occurs**</span></span>|<span data-ttu-id="88fa1-113">**Impacto**</span><span class="sxs-lookup"><span data-stu-id="88fa1-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88fa1-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="88fa1-114">**Active**</span></span>  <br/> |<span data-ttu-id="88fa1-115">El administrador ha cargado el complemento y lo ha asignado a usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="88fa1-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="88fa1-116">Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.</span><span class="sxs-lookup"><span data-stu-id="88fa1-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="88fa1-117">**Desactivado**</span><span class="sxs-lookup"><span data-stu-id="88fa1-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="88fa1-118">El administrador ha desactivado el complemento.</span><span class="sxs-lookup"><span data-stu-id="88fa1-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="88fa1-119">Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="88fa1-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="88fa1-120">Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.</span><span class="sxs-lookup"><span data-stu-id="88fa1-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="88fa1-121">**Eliminado**</span><span class="sxs-lookup"><span data-stu-id="88fa1-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="88fa1-122">El administrador ha eliminado el complemento.</span><span class="sxs-lookup"><span data-stu-id="88fa1-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="88fa1-123">Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="88fa1-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="88fa1-124">Considere la posibilidad de eliminar un complemento si no lo está usando ya.</span><span class="sxs-lookup"><span data-stu-id="88fa1-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="88fa1-125">Por ejemplo, la desactivación de un complemento puede tener sentido si se usa un complemento sólo durante determinados períodos del año.</span><span class="sxs-lookup"><span data-stu-id="88fa1-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="88fa1-126">Eliminar un complemento</span><span class="sxs-lookup"><span data-stu-id="88fa1-126">Delete an add-in</span></span>

<span data-ttu-id="88fa1-127">También puede eliminar un complemento que se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="88fa1-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="88fa1-128">En el centro de administración, vaya a **Settings**la página de los  >  **Complementos &** de los servicios de configuración.</span><span class="sxs-lookup"><span data-stu-id="88fa1-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="88fa1-129">Seleccione el complemento implementado.</span><span class="sxs-lookup"><span data-stu-id="88fa1-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="88fa1-130">Haga clic en **eliminar complemento**.</span><span class="sxs-lookup"><span data-stu-id="88fa1-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="88fa1-131">Quite el botón del complemento en la esquina inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="88fa1-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="88fa1-132">Valide las selecciones y elija **quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="88fa1-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="88fa1-133">Editar el acceso del complemento</span><span class="sxs-lookup"><span data-stu-id="88fa1-133">Edit add-in access</span></span>

<span data-ttu-id="88fa1-134">Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos.</span><span class="sxs-lookup"><span data-stu-id="88fa1-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="88fa1-135">En el centro de administración, vaya a **Settings**la página de los  >  **Complementos &** de los servicios de configuración.</span><span class="sxs-lookup"><span data-stu-id="88fa1-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="88fa1-136">Seleccione el complemento implementado.</span><span class="sxs-lookup"><span data-stu-id="88fa1-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="88fa1-137">Haga clic en **Editar** en la sección **¿quién tiene acceso**?</span><span class="sxs-lookup"><span data-stu-id="88fa1-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="88fa1-138">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="88fa1-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="88fa1-139">Impedir las descargas del complemento desactivando la tienda Office en todos los clientes (excepto Outlook)</span><span class="sxs-lookup"><span data-stu-id="88fa1-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="88fa1-140">La instalación de complementos de Outlook se administra mediante un [proceso diferente](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="88fa1-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="88fa1-141">Como organización, puede que quiera impedir la descarga de nuevos complementos de Office desde la tienda Office.</span><span class="sxs-lookup"><span data-stu-id="88fa1-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="88fa1-142">Esto puede usarse junto con la implementación centralizada para garantizar que solo los complementos aprobados por la organización se implementan para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="88fa1-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="88fa1-143">**Para desactivar la adquisición de complementos**</span><span class="sxs-lookup"><span data-stu-id="88fa1-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="88fa1-144">En el centro de administración, vaya a la página **Configuración** \>[de servicios &amp;complementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="88fa1-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="88fa1-145">Seleccione **aplicaciones y servicios de propiedad del usuario**.</span><span class="sxs-lookup"><span data-stu-id="88fa1-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="88fa1-146">Desactive la opción para permitir que los usuarios tengan acceso a la tienda Office.</span><span class="sxs-lookup"><span data-stu-id="88fa1-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="88fa1-147">Esto impedirá que todos los usuarios adquieran los siguientes complementos de la tienda.</span><span class="sxs-lookup"><span data-stu-id="88fa1-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="88fa1-148">Complementos para Word, Excel y PowerPoint 2016 desde:</span><span class="sxs-lookup"><span data-stu-id="88fa1-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="88fa1-149">Windows</span><span class="sxs-lookup"><span data-stu-id="88fa1-149">Windows</span></span>
    
  - <span data-ttu-id="88fa1-150">Mac</span><span class="sxs-lookup"><span data-stu-id="88fa1-150">Mac</span></span>
    
  - <span data-ttu-id="88fa1-151">Office</span><span class="sxs-lookup"><span data-stu-id="88fa1-151">Office</span></span>
    
    
- <span data-ttu-id="88fa1-152">Adquisiciones que comienzan dentro de **AppSource**</span><span class="sxs-lookup"><span data-stu-id="88fa1-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="88fa1-153">Complementos en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88fa1-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="88fa1-154">Un usuario que intente obtener acceso a la tienda verá el siguiente mensaje: **lo sentimos, Microsoft 365 se ha configurado para impedir la adquisición individual de complementos de la tienda Office.**</span><span class="sxs-lookup"><span data-stu-id="88fa1-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="88fa1-155">La compatibilidad para desactivar la tienda Office está disponible en las siguientes versiones:</span><span class="sxs-lookup"><span data-stu-id="88fa1-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="88fa1-156">Windows: 16.0.9001: actualmente disponible.</span><span class="sxs-lookup"><span data-stu-id="88fa1-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="88fa1-157">Mac: 16.10.18011401: actualmente disponible.</span><span class="sxs-lookup"><span data-stu-id="88fa1-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="88fa1-158">iOS: 2.9.18010804-actualmente disponible.</span><span class="sxs-lookup"><span data-stu-id="88fa1-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="88fa1-159">El Web actualmente disponible.</span><span class="sxs-lookup"><span data-stu-id="88fa1-159">The web - Currently available.</span></span>
    
<span data-ttu-id="88fa1-160">Esto no impide que un administrador use la implementación centralizada para asignar un complemento de la tienda Office.</span><span class="sxs-lookup"><span data-stu-id="88fa1-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="88fa1-161">Para evitar que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para usar solo la cuenta de la organización.</span><span class="sxs-lookup"><span data-stu-id="88fa1-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="88fa1-162">Para obtener más información, vea [identidad, autenticación y autorización en Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="88fa1-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="88fa1-163">Más información sobre la experiencia del usuario final con los complementos</span><span class="sxs-lookup"><span data-stu-id="88fa1-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="88fa1-164">Después de implementar un complemento, los usuarios finales pueden empezar a usarlo en sus aplicaciones de Office (consulte [empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="88fa1-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="88fa1-165">El complemento aparece en todas las plataformas admitidas por el complemento.</span><span class="sxs-lookup"><span data-stu-id="88fa1-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="88fa1-p107">Si el complemento es compatible con comandos de complemento, estos aparecerán en la cinta de opciones de Office. En el siguiente ejemplo, el comando **Buscar cita** aparece para el complemento **Citas**.</span><span class="sxs-lookup"><span data-stu-id="88fa1-p107">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Cinta de Office con citas de búsqueda](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="88fa1-169">Si el complemento implementado no es compatible con los comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través **de mis complementos**.</span><span class="sxs-lookup"><span data-stu-id="88fa1-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="88fa1-170">En Word 2016, Excel 2016 o PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="88fa1-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="88fa1-171">Seleccione **Insertar \> mis complementos**.</span><span class="sxs-lookup"><span data-stu-id="88fa1-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="88fa1-172">Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office.</span><span class="sxs-lookup"><span data-stu-id="88fa1-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="88fa1-173">Haga doble clic en el complemento que ha implementado antes (en este ejemplo, **Citas** ).</span><span class="sxs-lookup"><span data-stu-id="88fa1-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="88fa1-174">![Pestaña administrada de administración de la página de complementos de Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="88fa1-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="88fa1-175">En Outlook</span><span class="sxs-lookup"><span data-stu-id="88fa1-175">In Outlook</span></span>

1. <span data-ttu-id="88fa1-176">En la cinta de opciones **Inicio** , seleccione **obtener complementos**.</span><span class="sxs-lookup"><span data-stu-id="88fa1-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="88fa1-177">![Botón Tienda en Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="88fa1-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="88fa1-178">Seleccione **administrada por el administrador** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="88fa1-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="88fa1-179">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="88fa1-179">Learn more</span></span>

[<span data-ttu-id="88fa1-180">Implementar complementos en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="88fa1-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="88fa1-181">Obtenga más información sobre la creación y generación de [complementos de Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="88fa1-181">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="88fa1-182">[Use cmdlets de PowerShell de implementación centralizada para administrar complementos](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span><span class="sxs-lookup"><span data-stu-id="88fa1-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="88fa1-183">Solución de problemas: el usuario no ve complementos</span><span class="sxs-lookup"><span data-stu-id="88fa1-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="88fa1-184">Menores y adquisición de complementos de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="88fa1-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)