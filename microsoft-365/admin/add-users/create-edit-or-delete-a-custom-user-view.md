---
title: Crear, editar o eliminar una vista de usuario personalizada
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Aprenda a usar filtros para crear, editar o eliminar la vista de usuario personalizada en Microsoft 365.
ms.openlocfilehash: 598a167b9845f763ddab57d3c5ba36e431aa751c
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664579"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="8dae1-103">Crear, editar o eliminar una vista de usuario personalizada</span><span class="sxs-lookup"><span data-stu-id="8dae1-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="8dae1-104">Si es administrador global o de administración de usuarios de una suscripción a Microsoft 365 para empresas, puede crear vistas de usuario personalizadas para ver un subconjunto específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="8dae1-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="8dae1-105">Estas vistas se sume al conjunto estándar de vistas.</span><span class="sxs-lookup"><span data-stu-id="8dae1-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="8dae1-106">Puede crear, editar o eliminar vistas de usuario personalizadas y las vistas personalizadas que cree estarán disponibles para todos los administradores.</span><span class="sxs-lookup"><span data-stu-id="8dae1-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="8dae1-107">Vistas de usuario personalizadas en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="8dae1-107">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="8dae1-108">Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista de filtros que verán todos los administradores de su empresa cuando vayan a la página **Usuarios.** </span><span class="sxs-lookup"><span data-stu-id="8dae1-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="8dae1-109">Puede crear hasta 50 vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8dae1-109">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="8dae1-110">Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista Vistas que verán todos los administradores de su empresa cuando vayan a la página **Usuarios.** </span><span class="sxs-lookup"><span data-stu-id="8dae1-110">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="8dae1-111">Puede crear hasta 50 vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8dae1-111">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="8dae1-112">Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista Vistas que verán todos los administradores de su empresa cuando vayan a la página **Usuarios.** </span><span class="sxs-lookup"><span data-stu-id="8dae1-112">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="8dae1-113">Puede crear hasta 50 vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8dae1-113">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="8dae1-114">Las vistas de usuario estándar se muestran de forma predeterminada en **la** lista desplegable Filtros.</span><span class="sxs-lookup"><span data-stu-id="8dae1-114">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="8dae1-115">Los filtros estándar incluyen **Todos** los **usuarios,** Usuarios con **licencia,** Usuarios **invitados,** Inicio de sesión **permitido,** Inicio de sesión bloqueado **,** Usuarios sin **licencia,** Usuarios con **errores,** Administradores de facturación, Administradores **globales,** Administradores del departamento de soporte técnico, Administradores de servicio y Administradores de administración de **usuarios.** </span><span class="sxs-lookup"><span data-stu-id="8dae1-115">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="8dae1-116">No puede editar ni eliminar vistas estándar.</span><span class="sxs-lookup"><span data-stu-id="8dae1-116">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="8dae1-117">Algunos aspectos a tener en cuenta sobre las vistas estándar:</span><span class="sxs-lookup"><span data-stu-id="8dae1-117">A few things to note about standard views:</span></span> 

- <span data-ttu-id="8dae1-118">Algunas vistas estándar muestran una lista desordenada si hay más de 2.000 usuarios en la lista.</span><span class="sxs-lookup"><span data-stu-id="8dae1-118">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="8dae1-119">Para buscar usuarios específicos en esta lista, use el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8dae1-119">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="8dae1-120">Si no compró Microsoft 365 a **Microsoft,** los administradores de facturación no aparecerán en la lista de vistas estándar.</span><span class="sxs-lookup"><span data-stu-id="8dae1-120">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="8dae1-121">Para más información, vea [Asignar roles de administrador](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8dae1-121">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="8dae1-122">Elegir los filtros para la vista de usuario personalizada</span><span class="sxs-lookup"><span data-stu-id="8dae1-122">Choose the filters for your custom user view</span></span>

<span data-ttu-id="8dae1-123">Puede crear y editar las vistas personalizadas en el **panel filtro** personalizado.</span><span class="sxs-lookup"><span data-stu-id="8dae1-123">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="8dae1-124">Si selecciona varias opciones de filtro, obtiene resultados que contienen usuarios que coinciden con todos los criterios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="8dae1-124">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="8dae1-125">En el siguiente ejemplo se muestra cómo crear una vista personalizada denominada "Usuarios canadienses" que muestre todos los usuarios de un dominio específico que están en Canadá.</span><span class="sxs-lookup"><span data-stu-id="8dae1-125">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="8dae1-126">**A: dominio** Si tiene varios dominios para su organización, puede elegir entre una lista desplegable de dominios que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="8dae1-126">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="8dae1-127">**B: estado de inicio de sesión** Elija los usuarios que están permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="8dae1-127">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="8dae1-128">**C: ubicación** Elija una ubicación de una lista desplegable de países.</span><span class="sxs-lookup"><span data-stu-id="8dae1-128">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="8dae1-129">**D: licencia de producto asignada** Elija una lista desplegable de licencias disponibles en su organización.</span><span class="sxs-lookup"><span data-stu-id="8dae1-129">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="8dae1-130">Use este filtro para mostrar los usuarios que tienen asignada la licencia que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="8dae1-130">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="8dae1-131">Los usuarios también pueden tener licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="8dae1-131">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="8dae1-132">También puede filtrar por detalles de perfil de usuario adicionales usados en su organización, como departamento, ciudad, estado o provincia, país o región, o puesto.</span><span class="sxs-lookup"><span data-stu-id="8dae1-132">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="8dae1-133">**Otras condiciones:**</span><span class="sxs-lookup"><span data-stu-id="8dae1-133">**Other conditions:**</span></span>
  
- <span data-ttu-id="8dae1-134">**Solo usuarios sincronizados** Seleccione este cuadro para mostrar todos los usuarios que se han sincronizado con active Directory local, independientemente de si los usuarios se han activado o no.</span><span class="sxs-lookup"><span data-stu-id="8dae1-134">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="8dae1-135">**Usuarios con errores** Seleccione esta casilla para mostrar los usuarios que pueden tener errores de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="8dae1-135">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="8dae1-136">**Usuarios sin licencia** Seleccione esta casilla para buscar todos los usuarios a los que no se ha asignado una licencia.</span><span class="sxs-lookup"><span data-stu-id="8dae1-136">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="8dae1-137">Los resultados de esta vista también pueden incluir usuarios que tienen un buzón de Exchange pero no tienen una licencia.</span><span class="sxs-lookup"><span data-stu-id="8dae1-137">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="8dae1-138">Para realizar un seguimiento específico de esos usuarios, use el filtro usuarios sin licencia con **buzones o archivos de Exchange.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-138">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="8dae1-139">Los resultados de esta vista también pueden incluir usuarios que tienen un archivo de Exchange, pero no tienen una licencia.</span><span class="sxs-lookup"><span data-stu-id="8dae1-139">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="8dae1-140">**Usuarios sin licencia con buzones o archivos de Exchange** Seleccione esta casilla para mostrar las cuentas de usuario que se crearon en Exchange Online y que tienen un buzón de Exchange, pero que no se asignaron a una licencia de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8dae1-140">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="8dae1-141">Los resultados de este filtro incluyen usuarios que tienen o a los que se les asignó un archivo de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8dae1-141">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="8dae1-142">El **filtro de usuarios sin licencia con buzones de Exchange** funciona cuando:</span><span class="sxs-lookup"><span data-stu-id="8dae1-142">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="8dae1-143">El buzón se ha convertido recientemente de **compartido** a **usuario** y no tiene licencia.</span><span class="sxs-lookup"><span data-stu-id="8dae1-143">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="8dae1-144">El buzón se ha migrado recientemente a Microsoft 365, pero no se ha asignado una licencia.</span><span class="sxs-lookup"><span data-stu-id="8dae1-144">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="8dae1-145">El buzón se ha creado con PowerShell y no se ha asignado una licencia.</span><span class="sxs-lookup"><span data-stu-id="8dae1-145">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="8dae1-146">Se aprovisiona un nuevo buzón que se ha creado localmente con New-RemoteMailbox cmdlet para el usuario.</span><span class="sxs-lookup"><span data-stu-id="8dae1-146">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="8dae1-147">Si crea una vista personalizada que devuelve más de 2.000 usuarios, la lista de usuarios resultante no se ordena.</span><span class="sxs-lookup"><span data-stu-id="8dae1-147">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="8dae1-148">En este caso, use el cuadro de búsqueda para buscar usuarios o editar la vista personalizada para refinar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8dae1-148">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="8dae1-149">Crear una vista de usuario personalizada</span><span class="sxs-lookup"><span data-stu-id="8dae1-149">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8dae1-150">En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos.</a></span><span class="sxs-lookup"><span data-stu-id="8dae1-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="8dae1-151">En la **página Usuarios activos,** seleccione **Filtros** y **nuevo filtro.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-151">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="8dae1-152">En la **página Filtro** personalizado, escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8dae1-152">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="8dae1-153">La vista personalizada ahora se incluye en la lista desplegable de filtros.</span><span class="sxs-lookup"><span data-stu-id="8dae1-153">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8dae1-154">En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">activos.</a></span><span class="sxs-lookup"><span data-stu-id="8dae1-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="8dae1-155">En la **página Usuarios activos,** seleccione **Vistas** y agregar **vista personalizada.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="8dae1-156">En la **página Vista** personalizada, escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8dae1-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="8dae1-157">La vista personalizada ahora se incluye en la lista desplegable de filtros.</span><span class="sxs-lookup"><span data-stu-id="8dae1-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="8dae1-158">En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">activos.</a></span><span class="sxs-lookup"><span data-stu-id="8dae1-158">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="8dae1-159">En la **página Usuarios activos,** seleccione **Vistas** y agregar **vista personalizada.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-159">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="8dae1-160">En la **página Vista** personalizada, escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8dae1-160">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="8dae1-161">La vista personalizada ahora se incluye en la lista desplegable de filtros.</span><span class="sxs-lookup"><span data-stu-id="8dae1-161">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="8dae1-162">Editar o eliminar una vista de usuario personalizada</span><span class="sxs-lookup"><span data-stu-id="8dae1-162">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8dae1-163">En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos.</a></span><span class="sxs-lookup"><span data-stu-id="8dae1-163">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="8dae1-164">En la **página Usuarios activos,** seleccione **Filtro**, seleccione el filtro que desea cambiar y, a continuación, seleccione **Editar filtro.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-164">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8dae1-165">Solo puede editar vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8dae1-165">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="8dae1-166">En la **página Filtro** personalizado, edite la información según sea necesario y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8dae1-166">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="8dae1-167">O bien, para eliminar el filtro, en la parte inferior de la página seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8dae1-167">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8dae1-168">En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">activos.</a></span><span class="sxs-lookup"><span data-stu-id="8dae1-168">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="8dae1-169">En la **página Usuarios activos,** seleccione **Vistas**, seleccione el filtro que desea cambiar y, a continuación, seleccione Editar **esta vista.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-169">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8dae1-170">Solo puede editar vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8dae1-170">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="8dae1-171">En la **página Vista personalizada,** edite la información según sea necesario y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8dae1-171">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="8dae1-172">O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **Eliminar vista personalizada.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-172">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8dae1-173">En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">activos.</a></span><span class="sxs-lookup"><span data-stu-id="8dae1-173">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="8dae1-174">En la **página Usuarios activos,** seleccione **Vistas**, seleccione el filtro que desea cambiar y, a continuación, seleccione Editar **esta vista.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-174">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8dae1-175">Solo puede editar vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8dae1-175">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="8dae1-176">En la **página Vista personalizada,** edite la información según sea necesario y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8dae1-176">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="8dae1-177">O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **Eliminar vista personalizada.**</span><span class="sxs-lookup"><span data-stu-id="8dae1-177">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     