---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtenga información sobre cómo validar la configuración de protección de aplicaciones empresariales de Microsoft 365 en dispositivos Windows 10.
ms.openlocfilehash: 7710accf9a3cd1db788dd5215ab6d7bbb97e48a6
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074388"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="967eb-103">Validar la configuración de protección de aplicaciones en PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="967eb-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="967eb-104">Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="967eb-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="967eb-p101">Después de [configurar directivas de protección de la aplicación](protection-settings-for-windows-10-devices.md), puede tardar unas pocas horas en tener efecto la directiva en los dispositivos de los usuarios. Si ha **activado** la configuración **Impedir que los usuarios copien los datos de la compañía en los archivos personales y forzarlos a guardar los archivos de trabajo en OneDrive para la Empresa** para los dispositivos que son propiedad de la empresa, puede comprobarlo en el dispositivo del usuario después de que se hayan conectado a Azure AD e iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="967eb-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="967eb-107">**Comprobar la configuración de conexión**</span><span class="sxs-lookup"><span data-stu-id="967eb-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="967eb-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="967eb-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="967eb-111">En la página **Administrado por** \< nombre del inquilino \> puede ver la **información de conexión** que incluye una **dirección del servidor de administración** como la que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="967eb-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="967eb-113">**Compruebe que no puede pegar datos de la compañía a una aplicación no administrada**</span><span class="sxs-lookup"><span data-stu-id="967eb-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="967eb-114">Abra Outlook 2016 que fue instalada por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="967eb-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="967eb-115">Abra un correo electrónico y copie parte del contenido de él.</span><span class="sxs-lookup"><span data-stu-id="967eb-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="967eb-116">Abra el Bloc de notas e intente pegar el contenido.</span><span class="sxs-lookup"><span data-stu-id="967eb-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="967eb-117">Recibirá un error que indica que la aplicación no puede obtener acceso al contenido.</span><span class="sxs-lookup"><span data-stu-id="967eb-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="967eb-119">Sin embargo, puede pegar el mismo contenido en Word 2016.</span><span class="sxs-lookup"><span data-stu-id="967eb-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="967eb-120">Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos personales.</span><span class="sxs-lookup"><span data-stu-id="967eb-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="967eb-121">**Comprobar la configuración de conexión**</span><span class="sxs-lookup"><span data-stu-id="967eb-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="967eb-122">En el dispositivo personal de Windows 10 donde está conectado como un usuario local, vaya a **Configuración de Windows** y haga clic o pulse **Cuentas** \> **Acceso profesional o educativo**.</span><span class="sxs-lookup"><span data-stu-id="967eb-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="967eb-123">En **Acceso profesional o educativo**, elija **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="967eb-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="967eb-124">Escriba sus Microsoft 365 Business credenciales en el **diálogo Configurar una cuenta profesional o educativa** \> **Inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="967eb-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="967eb-125">En la página **Acceso profesional o educativo**, elija **Cuenta profesional o educativa** y, a continuación, elija **Información**.</span><span class="sxs-lookup"><span data-stu-id="967eb-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="967eb-127">En la página **Acceso profesional o educativo** puede ver **Información de conexión** que incluye una **dirección de servidor de administración** como la que se muestra en la siguiente imagen e incluye las palabras  *wip*  y  *mam*  .</span><span class="sxs-lookup"><span data-stu-id="967eb-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="967eb-129">**Compruebe que no puede pegar datos de la compañía a una aplicación no administrada**</span><span class="sxs-lookup"><span data-stu-id="967eb-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="967eb-130">Abra Outlook 2016 y agregue su Microsoft 365 Business cuenta si es necesario e inicie sesión con sus Microsoft 365 Business credenciales.</span><span class="sxs-lookup"><span data-stu-id="967eb-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="967eb-131">Abra un correo electrónico y copie parte del contenido de él.</span><span class="sxs-lookup"><span data-stu-id="967eb-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="967eb-132">Abra el Bloc de notas e intente pegar el contenido.</span><span class="sxs-lookup"><span data-stu-id="967eb-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="967eb-133">Recibirá un error que indica que la aplicación no puede obtener acceso al contenido.</span><span class="sxs-lookup"><span data-stu-id="967eb-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="967eb-135">Sin embargo, puede pegar el mismo contenido en Word 2016.</span><span class="sxs-lookup"><span data-stu-id="967eb-135">You can, however, paste the same content into Word 2016.</span></span>
    

