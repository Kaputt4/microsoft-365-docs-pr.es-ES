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
description: Obtenga información sobre cómo conservar los archivos y los correos electrónicos de un empleado cuando la persona abandona la organización.
ms.openlocfilehash: 38cc44bbe602f3c8c38ca54391d0967fbafbfcf7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906317"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="a0a7e-103">Obtener acceso y realizar una copia de seguridad de los datos de un antiguo usuario</span><span class="sxs-lookup"><span data-stu-id="a0a7e-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="a0a7e-104">Cuando un empleado deja la organización, probablemente quiera tener acceso a sus datos (documentos y correos electrónicos) y revisarlo, hacer una copia de seguridad o entregarlo a un nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="a0a7e-105">Obtener acceso a los documentos de OneDrive de un usuario anterior</span><span class="sxs-lookup"><span data-stu-id="a0a7e-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="a0a7e-106">Si quita la licencia de un usuario pero no elimina la cuenta, puede darnos acceso al contenido en OneDrive del usuario.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="a0a7e-107">Si elimina la cuenta del usuario, tiene 30 días de forma predeterminada para tener acceso a los datos de OneDrive del usuario anterior.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="a0a7e-108">[Obtenga información sobre cómo establecer la retención de OneDrive para usuarios eliminados.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="a0a7e-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="a0a7e-109">Si no restauras [una cuenta de usuario](/office365/admin/add-users/restore-user) en este tiempo, se elimina su contenido de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="a0a7e-110">Para conservar los archivos de OneDrive de un usuario anterior, primero dé acceso a su OneDrive y, a continuación, mueva los archivos que desee conservar.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a0a7e-111">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="a0a7e-112">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-112">Select a user.</span></span>

3. <span data-ttu-id="a0a7e-113">En el panel derecho, seleccione **OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-113">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="a0a7e-114">En **Obtener acceso a archivos,** seleccione Crear vínculo a **archivos**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-114">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="a0a7e-115">Seleccione el vínculo para abrir la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-115">Select the link to open the file location.</span></span> <span data-ttu-id="a0a7e-116">Descargue los archivos en el  equipo  o seleccione Mover a o Copiar para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-116">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="a0a7e-117">Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-117">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="a0a7e-118">Al mover o copiar documentos que tienen historial de versiones, solo se mueve la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-118">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a0a7e-119">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="a0a7e-120">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-120">Select a user.</span></span>

3. <span data-ttu-id="a0a7e-121">En el panel derecho, expanda **Configuración de OneDrive** y, a continuación, junto a **Access**, seleccione Archivos **de Access**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-121">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="a0a7e-122">Seleccione el vínculo para abrir la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-122">Select the link to open the file location.</span></span> <span data-ttu-id="a0a7e-123">Descargue los archivos en el  equipo  o seleccione Mover a o Copiar para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-123">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="a0a7e-124">Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-124">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="a0a7e-125">Al mover o copiar documentos que tienen historial de versiones, solo se mueve la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-125">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a0a7e-126">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="a0a7e-127">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-127">Select a user.</span></span>

3. <span data-ttu-id="a0a7e-128">En el panel derecho, expanda **Configuración de OneDrive** y, a continuación, junto a **Access**, seleccione Archivos **de Access**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-128">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="a0a7e-129">Seleccione el vínculo para abrir la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-129">Select the link to open the file location.</span></span> <span data-ttu-id="a0a7e-130">Descargue los archivos en el  equipo  o seleccione Mover a o Copiar para moverlos o copiarlos en su propio OneDrive o en una biblioteca compartida.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-130">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="a0a7e-131">Puede mover o copiar hasta 500 MB de archivos y carpetas a la vez.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-131">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="a0a7e-132">Al mover o copiar documentos que tienen historial de versiones, solo se mueve la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-132">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="a0a7e-133">Revocar el acceso de administrador a OneDrive de un usuario</span><span class="sxs-lookup"><span data-stu-id="a0a7e-133">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="a0a7e-134">Como administrador global, puedes darte acceso al contenido en OneDrive de un usuario, pero es posible que quieras quitar el acceso cuando ya no lo necesites.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-134">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a0a7e-135">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración</a> como administrador global o administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-135">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="a0a7e-136">Si recibe un mensaje de que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-136">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a0a7e-137">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración</a> como administrador global o administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-137">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="a0a7e-138">Si recibe un mensaje de que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-138">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a0a7e-139">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración</a> como administrador global o administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-139">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="a0a7e-140">Si recibe un mensaje de que no tiene permiso para acceder al centro de administración, no tiene permisos de administrador en su organización.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-140">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="a0a7e-141">En el panel izquierdo, seleccione **Centros de administración de** \> **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-141">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="a0a7e-142">(Es posible que deba seleccionar **Mostrar todo** para ver la lista de centros de administración).</span><span class="sxs-lookup"><span data-stu-id="a0a7e-142">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="a0a7e-143">Si aparece el centro de  administración clásico de SharePoint, seleccione Abrir ahora en la parte superior de la página para abrir el Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-143">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="a0a7e-144">En el panel izquierdo, seleccione **Más características**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-144">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="a0a7e-145">En **Perfiles de usuario,** seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-145">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="a0a7e-146">En **Personas,** seleccione **Administrar perfiles de usuario**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-146">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="a0a7e-147">Escriba el nombre del usuario y seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-147">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="a0a7e-148">Haga clic con el botón secundario en el usuario y, a continuación, **elija Administrar propietarios de colecciones de sitios**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-148">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="a0a7e-149">Quite la persona que ya no necesita acceso a los datos del usuario y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-149">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="a0a7e-150">Obtener acceso a los datos de Outlook de un usuario anterior</span><span class="sxs-lookup"><span data-stu-id="a0a7e-150">Access the Outlook data of a former user</span></span>

<span data-ttu-id="a0a7e-151">Para guardar los mensajes de correo electrónico, el calendario, las tareas y los contactos del antiguo empleado, exporte la información a un archivo de datos de Outlook (.pst).</span><span class="sxs-lookup"><span data-stu-id="a0a7e-151">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="a0a7e-152">[Agregue el correo electrónico del](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) antiguo empleado a Outlook (Si restablece la contraseña del usuario, puede establecerlo en algo que solo sepa). [](reset-passwords.md)</span><span class="sxs-lookup"><span data-stu-id="a0a7e-152">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="a0a7e-153">En Outlook, seleccione **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-153">In Outlook, select **File**.</span></span>
    
    ![Este es el aspecto de la cinta de opciones en Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="a0a7e-155">Seleccione **Abrir &amp; Exportar** \> **importación/exportación**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-155">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Comando Import/Export en la vista Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="a0a7e-157">Seleccione **Exportar a un archivo** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-157">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Exportar a una opción de archivo en el Asistente para importación y exportación](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="a0a7e-159">Seleccione **Archivo de datos de Outlook (.pst)** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-159">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="a0a7e-160">Seleccione la cuenta que desea exportar seleccionando el nombre o la dirección de correo electrónico, como Mailbox - Anne Weiler o anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-160">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="a0a7e-161">Si desea exportar todo lo que hay en su cuenta, incluido el correo, el calendario, los contactos, las tareas y las notas, asegúrese de que la casilla Incluir **subcarpetas** está activada.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-161">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a0a7e-162">Puede exportar una cuenta a la vez.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-162">You can export one account at a time.</span></span> <span data-ttu-id="a0a7e-163">Si desea exportar varias cuentas, después de exportar una cuenta, repita estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-163">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Cuadro de diálogo Exportar archivo de datos de Outlook con la carpeta superior seleccionada e Incluir subcarpetas activadas](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="a0a7e-165">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-165">Select **Next**.</span></span>
    
8. <span data-ttu-id="a0a7e-166">Seleccione **Examinar** para seleccionar dónde guardar el archivo de datos de Outlook (.pst).</span><span class="sxs-lookup"><span data-stu-id="a0a7e-166">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="a0a7e-167">Escriba un  *nombre de archivo* y, a continuación, seleccione **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-167">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a0a7e-168">Si ha usado la exportación antes, aparecerán la ubicación de la carpeta anterior y el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-168">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="a0a7e-169">Escriba un  *nombre de archivo diferente*  antes de seleccionar **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-169">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="a0a7e-170">Si va a exportar a un Archivo de datos de Outlook (.pst) existente, en **Opciones**, especifique qué desea hacer cuando exporte elementos que ya existen en el archivo.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-170">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="a0a7e-171">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-171">Select **Finish**.</span></span>
    
<span data-ttu-id="a0a7e-172">Outlook inicia la exportación inmediatamente a menos que se cree un nuevo archivo de datos de Outlook (.pst) o se utilice un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-172">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="a0a7e-173">Si está creando un archivo de datos de Outlook (.pst), una contraseña opcional puede ayudar a proteger el archivo.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-173">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="a0a7e-174">Cuando aparezca el cuadro de diálogo  Crear archivo de  datos de **Outlook,** escriba la contraseña en los cuadros Contraseña y Comprobar contraseña y, a continuación, **seleccione Aceptar**. </span><span class="sxs-lookup"><span data-stu-id="a0a7e-174">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="a0a7e-175">En el cuadro de diálogo Contraseña del archivo de datos de **Outlook,** escriba la  *contraseña* y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-175">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="a0a7e-176">Si está exportando a un archivo de datos de Outlook (.pst) existente protegido con contraseña, en el cuadro de diálogo Contraseña del archivo de datos de **Outlook,** escriba la contraseña y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-176">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="a0a7e-177">Vea cómo exportar o hacer una copia de seguridad del [correo electrónico, los contactos](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) y el calendario a un archivo .pst de Outlook en Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-177">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="a0a7e-178">De forma predeterminada, el correo electrónico está disponible sin conexión durante un período de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-178">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="a0a7e-179">Si es necesario, vea cómo aumentar [los datos disponibles sin conexión.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)</span><span class="sxs-lookup"><span data-stu-id="a0a7e-179">If required, see how to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="a0a7e-180">Dar acceso a otro usuario al correo electrónico de un usuario anterior</span><span class="sxs-lookup"><span data-stu-id="a0a7e-180">Give another user access to a former user's email</span></span> 

<span data-ttu-id="a0a7e-181">Para dar acceso a los mensajes de correo electrónico, el calendario, las tareas y los contactos del antiguo empleado a otro empleado, importe la información a la bandeja de entrada de Outlook de otro empleado.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-181">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="a0a7e-182">También puede convertir [el buzón del usuario](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) anterior en un buzón compartido o reenviar el correo electrónico de un antiguo empleado a otro [empleado](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="a0a7e-182">You can also [convert the former user's mailbox to a shared mailbox](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="a0a7e-183">En Outlook, vaya **a Archivo** \> **Abrir &amp; exportación** \> **Importar/Exportar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-183">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="a0a7e-184">Esto inicia el Asistente para importación y exportación.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-184">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="a0a7e-185">Seleccione **Importar desde otro programa o archivo y,** a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-185">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Asistente para importación y exportación](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="a0a7e-187">Seleccione **Archivo de datos de Outlook (.pst)** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-187">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="a0a7e-188">Vaya al archivo .pst que desea importar.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-188">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="a0a7e-189">En **Opciones,** elija cómo desea tratar con duplicados</span><span class="sxs-lookup"><span data-stu-id="a0a7e-189">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="a0a7e-190">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-190">Select **Next**.</span></span>
    
7. <span data-ttu-id="a0a7e-191">Si se asignó una contraseña al archivo de datos de Outlook (.pst), escriba la contraseña y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-191">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="a0a7e-192">Establezca las opciones para importar elementos.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-192">Set the options for importing items.</span></span> <span data-ttu-id="a0a7e-193">Normalmente, no es necesario cambiar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-193">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="a0a7e-194">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-194">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="a0a7e-195">Los pasos siguen siendo los mismos para obtener acceso a los datos de OneDrive y correo electrónico de un usuario existente.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-195">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="a0a7e-196">Si desea importar o restaurar solo algunos elementos de un archivo de datos de Outlook (.pst), puede abrir el archivo de datos de Outlook.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-196">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="a0a7e-197">A continuación, en el panel de navegación, arrastre los elementos de las carpetas del archivo de datos de Outlook a las carpetas existentes de Outlook.</span><span class="sxs-lookup"><span data-stu-id="a0a7e-197">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="a0a7e-198">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a0a7e-198">Related articles</span></span>
[<span data-ttu-id="a0a7e-199">Quitar un antiguo empleado de Office 365</span><span class="sxs-lookup"><span data-stu-id="a0a7e-199">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="a0a7e-200">Agregar y quitar administradores en una cuenta de OneDrive</span><span class="sxs-lookup"><span data-stu-id="a0a7e-200">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="a0a7e-201">Restaurar un OneDrive eliminado</span><span class="sxs-lookup"><span data-stu-id="a0a7e-201">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="a0a7e-202">Retención y eliminación de OneDrive</span><span class="sxs-lookup"><span data-stu-id="a0a7e-202">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
