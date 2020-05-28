---
title: Obtener acceso y realizar una copia de seguridad de los datos de un antiguo usuario
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Obtenga información sobre cómo preservar los archivos y los correos electrónicos de un empleado cuando la persona abandone la organización.
ms.openlocfilehash: 2bf32aa9e7a3dcc76ae2114240bff07d697ce29d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387206"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="c08a2-103">Obtener acceso y realizar una copia de seguridad de los datos de un antiguo usuario</span><span class="sxs-lookup"><span data-stu-id="c08a2-103">Get access to and back up a former user's data</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c08a2-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="c08a2-104">The admin center is changing.</span></span> <span data-ttu-id="c08a2-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c08a2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end


<span data-ttu-id="c08a2-106">Cuando un empleado deja la organización, es probable que desee tener acceso a sus datos (documentos y correos electrónicos) y revisarlos, realizar una copia de seguridad o asignarlos a un nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="c08a2-106">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="c08a2-107">Obtener acceso a los documentos de OneDrive del usuario anterior</span><span class="sxs-lookup"><span data-stu-id="c08a2-107">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="c08a2-108">Si quita la licencia de un usuario pero no la elimina, puede conceder acceso al contenido del OneDrive del usuario.</span><span class="sxs-lookup"><span data-stu-id="c08a2-108">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="c08a2-109">Si elimina la cuenta de usuario, tiene 30 días de manera predeterminada para obtener acceso a los datos de OneDrive del usuario anterior.</span><span class="sxs-lookup"><span data-stu-id="c08a2-109">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="c08a2-110">[Obtenga información sobre cómo configurar la retención de OneDrive para los usuarios eliminados](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="c08a2-110">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="c08a2-111">Si no [restaura una cuenta de usuario](/office365/admin/add-users/restore-user) en este momento, se eliminará su contenido de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c08a2-111">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="c08a2-112">Para conservar los archivos de OneDrive de un usuario anterior, primero se debe conceder acceso a su OneDrive y, a continuación, mover los archivos que desee conservar.</span><span class="sxs-lookup"><span data-stu-id="c08a2-112">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c08a2-113">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="c08a2-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="c08a2-114">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="c08a2-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="c08a2-115">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="c08a2-115">Select a user.</span></span>

3. <span data-ttu-id="c08a2-116">En el panel derecho, seleccione **OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-116">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="c08a2-117">En **obtener acceso a los archivos**, seleccione **crear vínculo a archivos**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-117">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="c08a2-118">Seleccione el vínculo para abrir la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="c08a2-118">Select the link to open the file location.</span></span> <span data-ttu-id="c08a2-119">Descargue los archivos en el equipo o seleccione **mover a** o **copiar a** para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.</span><span class="sxs-lookup"><span data-stu-id="c08a2-119">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="c08a2-120">Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.</span><span class="sxs-lookup"><span data-stu-id="c08a2-120">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="c08a2-121">Al mover o copiar documentos que tienen el historial de versiones, solo se mueve la última versión.</span><span class="sxs-lookup"><span data-stu-id="c08a2-121">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c08a2-122">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="c08a2-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="c08a2-123">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="c08a2-123">Select a user.</span></span>

3. <span data-ttu-id="c08a2-124">En el panel derecho, expanda **configuración de OneDrive**y, después, junto a **acceso**, seleccione **Access files**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-124">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="c08a2-125">Seleccione el vínculo para abrir la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="c08a2-125">Select the link to open the file location.</span></span> <span data-ttu-id="c08a2-126">Descargue los archivos en el equipo o seleccione **mover a** o **copiar a** para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.</span><span class="sxs-lookup"><span data-stu-id="c08a2-126">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="c08a2-127">Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.</span><span class="sxs-lookup"><span data-stu-id="c08a2-127">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="c08a2-128">Al mover o copiar documentos que tienen el historial de versiones, solo se mueve la última versión.</span><span class="sxs-lookup"><span data-stu-id="c08a2-128">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c08a2-129">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="c08a2-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="c08a2-130">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="c08a2-130">Select a user.</span></span>

3. <span data-ttu-id="c08a2-131">En el panel derecho, expanda **configuración de OneDrive**y, después, junto a **acceso**, seleccione **Access files**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-131">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="c08a2-132">Seleccione el vínculo para abrir la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="c08a2-132">Select the link to open the file location.</span></span> <span data-ttu-id="c08a2-133">Descargue los archivos en el equipo o seleccione **mover a** o **copiar a** para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.</span><span class="sxs-lookup"><span data-stu-id="c08a2-133">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="c08a2-134">Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.</span><span class="sxs-lookup"><span data-stu-id="c08a2-134">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="c08a2-135">Al mover o copiar documentos que tienen el historial de versiones, solo se mueve la última versión.</span><span class="sxs-lookup"><span data-stu-id="c08a2-135">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="c08a2-136">Revocar el acceso de administrador al OneDrive de un usuario</span><span class="sxs-lookup"><span data-stu-id="c08a2-136">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="c08a2-137">Como administrador global, puede dar acceso al contenido en el OneDrive de un usuario, pero es posible que quiera quitar el acceso cuando ya no lo necesite.</span><span class="sxs-lookup"><span data-stu-id="c08a2-137">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c08a2-138">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a> como administrador global o administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c08a2-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="c08a2-139">Si recibe un mensaje que indica que no tiene permiso para obtener acceso al centro de administración, no tiene permisos de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="c08a2-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c08a2-140">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a> como administrador global o administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c08a2-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="c08a2-141">Si recibe un mensaje que indica que no tiene permiso para obtener acceso al centro de administración, no tiene permisos de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="c08a2-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c08a2-142">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a> como administrador global o administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c08a2-142">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="c08a2-143">Si recibe un mensaje que indica que no tiene permiso para obtener acceso al centro de administración, no tiene permisos de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="c08a2-143">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="c08a2-144">En el panel izquierdo, seleccione **centros de administración** \> **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-144">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="c08a2-145">(Es posible que deba seleccionar **Mostrar todo** para ver la lista de centros de administración).</span><span class="sxs-lookup"><span data-stu-id="c08a2-145">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="c08a2-146">Si se muestra el Centro de administración de SharePoint clásico, seleccione **Abrirlo ahora** en la parte superior de la página para abrir el nuevo Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c08a2-146">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="c08a2-147">En el panel izquierdo, seleccione **más características**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-147">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="c08a2-148">En **perfiles de usuario**, seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-148">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="c08a2-149">En **personas**, seleccione **administrar perfiles de usuario**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-149">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="c08a2-150">Escriba el nombre del usuario y seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-150">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="c08a2-151">Haga clic con el botón secundario en el usuario y elija **Administrar propietarios**de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="c08a2-151">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="c08a2-152">Quite a la persona que ya no necesita acceso a los datos del usuario y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-152">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="c08a2-153">Obtener acceso a los datos de Outlook de un usuario anterior</span><span class="sxs-lookup"><span data-stu-id="c08a2-153">Access the Outlook data of a former user</span></span>

<span data-ttu-id="c08a2-154">Para guardar los mensajes de correo electrónico, el calendario, las tareas y los contactos del antiguo empleado, exporte la información a un archivo de datos de Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="c08a2-154">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="c08a2-155">[Agregue el correo electrónico del antiguo empleado](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) a su Outlook (si [restablece la contraseña del usuario](reset-passwords.md), puede establecerla en algo que solo usted sabrá).</span><span class="sxs-lookup"><span data-stu-id="c08a2-155">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="c08a2-156">En Outlook, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-156">In Outlook, select **File**.</span></span>
    
    ![Este es el aspecto de la cinta en Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="c08a2-158">Seleccione \*\*abrir &amp; \*\* \> **importación/exportación**de exportación.</span><span class="sxs-lookup"><span data-stu-id="c08a2-158">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Comando importar o exportar en la vista backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="c08a2-160">Seleccione **exportar a un archivo**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-160">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Opción exportar a un archivo en el Asistente para importar y exportar](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="c08a2-162">Seleccione **archivo de datos de Outlook (. pst)** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-162">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="c08a2-163">Seleccione la cuenta que desea exportar seleccionando el nombre o la dirección de correo electrónico, como Mailbox-Cecilia Weiler o anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c08a2-163">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="c08a2-164">Si desea exportar todo el en su cuenta, incluido el correo, el calendario, los contactos, las tareas y las notas, asegúrese de que la casilla de verificación **Incluir subcarpetas** está activada.</span><span class="sxs-lookup"><span data-stu-id="c08a2-164">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c08a2-165">Puede exportar una cuenta a la vez.</span><span class="sxs-lookup"><span data-stu-id="c08a2-165">You can export one account at a time.</span></span> <span data-ttu-id="c08a2-166">Si desea exportar varias cuentas, después de que se exporte una cuenta, repita estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c08a2-166">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Cuadro de diálogo Exportar archivo de datos de Outlook con la carpeta superior seleccionada e incluir las subcarpetas seleccionadas](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="c08a2-168">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-168">Select **Next**.</span></span>
    
8. <span data-ttu-id="c08a2-169">Seleccione **examinar** para seleccionar dónde guardar el archivo de datos de Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="c08a2-169">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="c08a2-170">Escriba un *nombre de archivo*y, después, haga clic en **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="c08a2-170">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c08a2-171">Si ha usado exportar antes, aparecerán la ubicación de la carpeta y el nombre de archivo anteriores.</span><span class="sxs-lookup"><span data-stu-id="c08a2-171">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="c08a2-172">Escriba un *nombre de archivo diferente* antes de seleccionar **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-172">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="c08a2-173">Si va a exportar a un Archivo de datos de Outlook (.pst) existente, en **Opciones**, especifique qué desea hacer cuando exporte elementos que ya existen en el archivo.</span><span class="sxs-lookup"><span data-stu-id="c08a2-173">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="c08a2-174">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-174">Select **Finish**.</span></span>
    
<span data-ttu-id="c08a2-175">Outlook comienza la exportación inmediatamente a menos que se cree un nuevo archivo de datos de Outlook (. pst) o se use un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="c08a2-175">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="c08a2-176">Si va a crear un archivo de datos de Outlook (. pst), una contraseña opcional puede ayudarle a proteger el archivo.</span><span class="sxs-lookup"><span data-stu-id="c08a2-176">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="c08a2-177">Cuando aparezca el cuadro de diálogo **crear archivo de datos de Outlook** , escriba la *contraseña* en los cuadros **contraseña** y **Confirmar contraseña** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-177">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="c08a2-178">En el cuadro de diálogo **contraseña de archivo de datos de Outlook** , escriba la *contraseña*y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-178">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="c08a2-179">Si está exportando a un archivo de datos de Outlook (. pst) existente que está protegido con contraseña, en el cuadro de diálogo **contraseña de archivo de datos de Outlook** , escriba la *contraseña*y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-179">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="c08a2-180">Vea cómo [exportar o hacer una copia de seguridad del correo electrónico, los contactos y el calendario en un archivo. pst de Outlook](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) en Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="c08a2-180">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="c08a2-181">De forma predeterminada, el correo electrónico está disponible sin conexión durante un período de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="c08a2-181">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="c08a2-182">Si es necesario, vea cómo [aumentar los datos disponibles sin conexión](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="c08a2-182">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="c08a2-183">Proporcionar a otro usuario acceso al correo electrónico de un usuario anterior</span><span class="sxs-lookup"><span data-stu-id="c08a2-183">Give another user access to a former user's email</span></span> 

<span data-ttu-id="c08a2-184">Para conceder acceso a los mensajes de correo electrónico, el calendario, las tareas y los contactos del antiguo empleado a otro empleado, importe la información a la bandeja de entrada de Outlook de otro empleado.</span><span class="sxs-lookup"><span data-stu-id="c08a2-184">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="c08a2-185">También puede [convertir el buzón del usuario anterior en un buzón compartido](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) o [reenviar el correo electrónico de un antiguo empleado a otro empleado](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="c08a2-185">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="c08a2-186">En Outlook, vaya a **archivo** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-186">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="c08a2-187">Se iniciará el Asistente para importar y exportar.</span><span class="sxs-lookup"><span data-stu-id="c08a2-187">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="c08a2-188">Seleccione **Importar desde otro programa o archivo**y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-188">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Asistente para importar y exportar](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="c08a2-190">Seleccione **archivo de datos de Outlook (. pst)** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-190">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="c08a2-191">Vaya al archivo. pst que desea importar.</span><span class="sxs-lookup"><span data-stu-id="c08a2-191">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="c08a2-192">En **Opciones**, elija cómo desea tratar los duplicados</span><span class="sxs-lookup"><span data-stu-id="c08a2-192">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="c08a2-193">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-193">Select **Next**.</span></span>
    
7. <span data-ttu-id="c08a2-194">Si se asignó una contraseña al archivo de datos de Outlook (. pst), escriba la contraseña y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-194">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="c08a2-195">Establezca las opciones para importar elementos.</span><span class="sxs-lookup"><span data-stu-id="c08a2-195">Set the options for importing items.</span></span> <span data-ttu-id="c08a2-196">Por lo general, no es necesario cambiar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c08a2-196">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="c08a2-197">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c08a2-197">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="c08a2-198">Los pasos siguen siendo los mismos para obtener acceso a los datos de OneDrive y correo electrónico de un usuario existente.</span><span class="sxs-lookup"><span data-stu-id="c08a2-198">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="c08a2-199">Si desea importar o restaurar sólo algunos elementos de un archivo de datos de Outlook (. pst), puede abrir el archivo de datos de Outlook.</span><span class="sxs-lookup"><span data-stu-id="c08a2-199">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="c08a2-200">A continuación, en el panel de navegación, arrastre los elementos de las carpetas de archivos de datos de Outlook a las carpetas de Outlook existentes.</span><span class="sxs-lookup"><span data-stu-id="c08a2-200">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="c08a2-201">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="c08a2-201">Related articles</span></span>
[<span data-ttu-id="c08a2-202">Quitar un antiguo empleado de Office 365</span><span class="sxs-lookup"><span data-stu-id="c08a2-202">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="c08a2-203">Agregar y quitar administradores en una cuenta de OneDrive</span><span class="sxs-lookup"><span data-stu-id="c08a2-203">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="c08a2-204">Restaurar un OneDrive eliminado</span><span class="sxs-lookup"><span data-stu-id="c08a2-204">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="c08a2-205">Retención y eliminación de OneDrive</span><span class="sxs-lookup"><span data-stu-id="c08a2-205">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
