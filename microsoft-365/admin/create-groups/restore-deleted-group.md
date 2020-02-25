---
title: Restaurar un grupo de Office 365 eliminado
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Obtenga información sobre cómo restaurar un grupo de Office 365 eliminado mediante el centro de administración de Exchange. '
ms.openlocfilehash: 98eb00d90f5b607a58cd32728ce43cb4a1de1ff5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246556"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="ef819-103">Restaurar un grupo de Office 365 eliminado</span><span class="sxs-lookup"><span data-stu-id="ef819-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="ef819-104">Si es el propietario de un grupo de Office 365, puede restaurar el grupo mediante los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="ef819-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="ef819-105">En la [Página grupos eliminados](https://outlook.office.com/people/group/deleted), seleccione la opción **administrar grupos** en el nodo **grupos** y, a continuación, elija **eliminado**.</span><span class="sxs-lookup"><span data-stu-id="ef819-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="ef819-106">Haga clic en la pestaña **restaurar** situada junto al grupo que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="ef819-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="ef819-107">Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.</span><span class="sxs-lookup"><span data-stu-id="ef819-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="ef819-108">Si es un usuario que desea restaurar un grupo de Office 365, pida a un administrador que siga estos pasos para usted o póngase en contacto con el Departamento de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ef819-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="ef819-109">Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ef819-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="ef819-110">Este período de 30 días se considera una "eliminación temporal" porque todavía puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="ef819-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="ef819-111">Transcurrido el plazo de 30 días, el grupo y su contenido asociado se eliminan de forma permanente y no se pueden restaurar.</span><span class="sxs-lookup"><span data-stu-id="ef819-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="ef819-112">Durante el período "Soft-delete", si un usuario intenta acceder al sitio, recibirá un mensaje 404 _prohibido_ .</span><span class="sxs-lookup"><span data-stu-id="ef819-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="ef819-113">Después de este período, si un usuario intenta acceder al sitio, recibirá un mensaje 404 _no encontrado_ .</span><span class="sxs-lookup"><span data-stu-id="ef819-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="ef819-114">Cuando se restaura un grupo, se restaura el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="ef819-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="ef819-115">Azure Active Directory (AD) Office 365 Groups (objeto, propiedades y miembros).</span><span class="sxs-lookup"><span data-stu-id="ef819-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="ef819-116">Direcciones de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="ef819-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="ef819-117">Bandeja de entrada y calendario compartidos de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef819-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="ef819-118">Sitio de grupo y archivos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef819-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="ef819-119">Bloc de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="ef819-119">OneNote notebook</span></span>
    
- <span data-ttu-id="ef819-120">Planner</span><span class="sxs-lookup"><span data-stu-id="ef819-120">Planner</span></span>
    
- <span data-ttu-id="ef819-121">Teams</span><span class="sxs-lookup"><span data-stu-id="ef819-121">Teams</span></span>

- <span data-ttu-id="ef819-122">Grupo de Yammer y contenido del grupo (si se creó el grupo de Office 365 desde Yammer)</span><span class="sxs-lookup"><span data-stu-id="ef819-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="ef819-123">También puede [Eliminar permanentemente un grupo de Office 365](#permanently-delete-an-office-365-group) si no puede esperar a que expire el período de retención de 30 días para que se elimine el contenido de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="ef819-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="ef819-124">El propietario del grupo Office 365 eliminado también puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="ef819-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="ef819-125">Para restaurar un grupo de Office 365 mediante permiso de propietario sin permiso de administrador, vea [restaurar un grupo de office 365 con PowerShell](#restore-an-office-365-group-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="ef819-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="ef819-126">Restaurar un grupo de Office 365 con el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="ef819-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="ef819-127">Debe tener permisos de administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef819-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="ef819-128">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="ef819-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="ef819-129">En el Centro de administración de Exchange, seleccione **destinatarios** y, luego, elija **grupos**.</span><span class="sxs-lookup"><span data-stu-id="ef819-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="ef819-130">Puede ver si el grupo está activo o eliminado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="ef819-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="ef819-131">Si el grupo se ha eliminado de forma permanente, directamente no aparecerá.</span><span class="sxs-lookup"><span data-stu-id="ef819-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="ef819-132">Para ver el tiempo exacto en el que se eliminó el grupo de forma temporal, seleccione el grupo y vea la información en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="ef819-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="ef819-133">Seleccione el grupo que desea restaurar y, a continuación, seleccione el icono restaurar.</span><span class="sxs-lookup"><span data-stu-id="ef819-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![Elija el grupo que desea restaurar y, a continuación, seleccione el icono restaurar.](../media/restore-group.png)
  
5. <span data-ttu-id="ef819-135">Seleccione actualizar</span><span class="sxs-lookup"><span data-stu-id="ef819-135">Select refresh</span></span> ![Icono Actualizar](../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="ef819-137">para actualizar la información de la página.</span><span class="sxs-lookup"><span data-stu-id="ef819-137">to update the information on the page.</span></span> <span data-ttu-id="ef819-138">El grupo se mostrará como Activo.</span><span class="sxs-lookup"><span data-stu-id="ef819-138">Your group will show as Active.</span></span> <span data-ttu-id="ef819-139">También se restaurarán los formularios y los datos de formulario asociados con su grupo.</span><span class="sxs-lookup"><span data-stu-id="ef819-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="ef819-140">Restaurar un grupo de Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef819-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="ef819-141">Debe tener los permisos de administrador global de Office 365 o ser un antiguo propietario del grupo de Office 365 eliminado.</span><span class="sxs-lookup"><span data-stu-id="ef819-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef819-142">Si usa Remove-MsolGroup en PowerShell para eliminar un grupo, se eliminará el grupo de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="ef819-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="ef819-143">Al usar PowerShell para eliminar grupos, se recomienda usar **Remove-AzureADMSGroup** para eliminar temporalmente el grupo de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef819-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="ef819-144">De este modo, lo podrá restaurar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ef819-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="ef819-145">Instalación de la versión preliminar de Azure Active Directory PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="ef819-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef819-146">No puede instalar la versión preliminar y la versión GA en el mismo equipo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ef819-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="ef819-147">Como procedimiento recomendado, se recomienda mantenerse *siempre* actualizado, es decir, desinstalar la versión antigua de AzureADPreview o la versión de AzureAD anterior y obtener la última.</span><span class="sxs-lookup"><span data-stu-id="ef819-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="ef819-148">En la barra de búsqueda, escriba Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef819-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="ef819-149">Haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ef819-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="ef819-150">Revise los módulos instalados:</span><span class="sxs-lookup"><span data-stu-id="ef819-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="ef819-151">Para desinstalar una versión anterior de AzureADPreview o AzureAD, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="ef819-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="ef819-152">o bien</span><span class="sxs-lookup"><span data-stu-id="ef819-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="ef819-153">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="ef819-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="ef819-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="ef819-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="ef819-155">Restaurar el grupo eliminado</span><span class="sxs-lookup"><span data-stu-id="ef819-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="ef819-156">¿Ha instalado el módulo **AzureADPreview** , tal y como se indica en la sección Previoius "instalar la versión preliminar del módulo Azure Active Directory para Windows PowerShell"?</span><span class="sxs-lookup"><span data-stu-id="ef819-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="ef819-157">No tener instalada la versión **preliminar** más actual es la razón número 1 para que estos pasos no funcionen.</span><span class="sxs-lookup"><span data-stu-id="ef819-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="ef819-158">Si todavía no lo ha hecho, abra una ventana de Windows PowerShell en el equipo (no importa si es una ventana de Windows PowerShell normal o una que haya abierto mediante la selección de **Ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="ef819-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="ef819-159">Ejecute los siguientes comandos presionando **entrar** después de cada uno:</span><span class="sxs-lookup"><span data-stu-id="ef819-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="ef819-160">En la pantalla **iniciar sesión en su cuenta** que se abre, escriba el nombre de usuario y la contraseña de la cuenta administrativa para conectar con el servicio de Azure ad y seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="ef819-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="ef819-161">Ejecute este comando para mostrar todos los grupos de Office 365 eliminados temporalmente de la organización que aún están en el período de eliminación de software de 30 días:</span><span class="sxs-lookup"><span data-stu-id="ef819-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="ef819-162">Anote el identificador de objeto del grupo o grupos que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="ef819-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="ef819-163">Si no ve el grupo que está buscando en esta lista, es probable que ya se haya purgado de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="ef819-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ef819-164">Si se ha creado un grupo nuevo con el mismo alias o la misma dirección SMTP que el grupo eliminado, tendrá que eliminar el grupo nuevo antes de poder restaurar el grupo eliminado.</span><span class="sxs-lookup"><span data-stu-id="ef819-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="ef819-165">Para restaurar ese grupo, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="ef819-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="ef819-166">Este proceso suele durar sólo unos minutos pero, en algunos casos raros, puede tardar hasta 24 horas en restaurarse completamente.</span><span class="sxs-lookup"><span data-stu-id="ef819-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="ef819-167">Para comprobar que el grupo se ha restaurado correctamente, ejecute este comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ef819-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="ef819-p110">Una vez que la restauración se haya completado correctamente, el grupo debería aparecer de nuevo en el panel de navegación de Outlook y Outlook en la Web. Todo el contenido restaurado, incluido el de SharePoint y Planner, debería volver a estar disponible para los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="ef819-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="ef819-170">Eliminar permanentemente un grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="ef819-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="ef819-171">A veces, es posible que desee purgar un grupo de forma permanente sin esperar a que expire el período de eliminación de software de 30 días.</span><span class="sxs-lookup"><span data-stu-id="ef819-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="ef819-172">Para ello, inicie PowerShell y ejecute este comando para obtener el identificador de objeto del Grupo:</span><span class="sxs-lookup"><span data-stu-id="ef819-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="ef819-173">Anote el identificador de objeto del grupo o grupos que desea eliminar de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="ef819-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ef819-174">Purgar el grupo elimina el grupo y sus datos para siempre.</span><span class="sxs-lookup"><span data-stu-id="ef819-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="ef819-175">Para purgar el grupo, ejecute este comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ef819-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="ef819-p112">Para confirmar que el grupo se ha purgado correctamente, ejecute el cmdlet  *Get-AzureADMSDeletedGroup*  de nuevo para confirmar que el grupo ya no aparece en la lista de grupos eliminados temporalmente. En algunos casos, la eliminación permanente del grupo y todos sus datos puede tardar hasta 24 horas.</span><span class="sxs-lookup"><span data-stu-id="ef819-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="ef819-178">¿Tiene preguntas sobre los grupos de Office 365?</span><span class="sxs-lookup"><span data-stu-id="ef819-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="ef819-179">Visite [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef819-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="ef819-180">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="ef819-180">Related articles</span></span>

[<span data-ttu-id="ef819-181">Administrar grupos de Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef819-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="ef819-182">Eliminar grupos mediante el cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="ef819-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="ef819-183">Administrar la configuración de su sitio de grupo conectado</span><span class="sxs-lookup"><span data-stu-id="ef819-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="ef819-184">Eliminar un grupo en Outlook</span><span class="sxs-lookup"><span data-stu-id="ef819-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
