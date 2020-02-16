---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
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
ms.openlocfilehash: 577921f7f33eafbbe652dcf825a145d89f1ff556
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42057354"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="99048-103">Validar la configuración de protección de aplicaciones en PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="99048-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="99048-104">Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="99048-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="99048-105">Después de [configurar directivas de protección de la aplicación](protection-settings-for-windows-10-devices.md), puede tardar unas pocas horas en tener efecto la directiva en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="99048-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="99048-106">Si **activó la** opción evitar que **los usuarios copien los datos de la compañía en archivos personales y forzar que se guarden los archivos de trabajo en OneDrive para** la empresa para los dispositivos que son propiedad de la empresa, puede comprobarlo en el dispositivo del usuario después de que se hayan conectado a Azure ad y hayan iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="99048-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="99048-107">**Comprobar la configuración de conexión**</span><span class="sxs-lookup"><span data-stu-id="99048-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="99048-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="99048-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="99048-111">En la página **administrado por** \<nombre\> de espacio empresarial, puede ver la **información de conexión** que incluye una dirección del servidor de **Administración** como la que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="99048-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="99048-113">**Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**</span><span class="sxs-lookup"><span data-stu-id="99048-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="99048-114">Abra Outlook 2016 que fue instalada por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="99048-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="99048-115">Abra un correo electrónico y copie parte del contenido de él.</span><span class="sxs-lookup"><span data-stu-id="99048-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="99048-116">Abra el Bloc de notas e intente pegar el contenido.</span><span class="sxs-lookup"><span data-stu-id="99048-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="99048-117">Recibirá un error que indica que la aplicación no puede acceder al contenido.</span><span class="sxs-lookup"><span data-stu-id="99048-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="99048-119">Sin embargo, puede pegar el mismo contenido en Word 2016.</span><span class="sxs-lookup"><span data-stu-id="99048-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="99048-120">Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos personales.</span><span class="sxs-lookup"><span data-stu-id="99048-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="99048-121">**Comprobar la configuración de conexión**</span><span class="sxs-lookup"><span data-stu-id="99048-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="99048-122">En el dispositivo de Windows 10 personal en el que haya iniciado sesión como usuario local, vaya **a configuración de Windows**y haga clic o pulse **cuentas** \> de **acceso profesional o educativa**.</span><span class="sxs-lookup"><span data-stu-id="99048-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="99048-123">En **Acceso profesional o educativo**, elija **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="99048-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="99048-124">Escriba sus Microsoft 365 Business credenciales en el **diálogo Configurar una cuenta profesional o educativa** \> **Inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="99048-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="99048-125">En la página **Acceso profesional o educativo**, elija **Cuenta profesional o educativa** y, a continuación, elija **Información**.</span><span class="sxs-lookup"><span data-stu-id="99048-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Haga clic o pulse en información en el cuadro de diálogo de la cuenta profesional o educativa.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="99048-127">En la página **tener acceso a la escuela o el trabajo** , puede ver la **información de conexión** que incluye una dirección del servidor de **Administración** como la que se muestra en la figura siguiente, e incluye las palabras *WIP* y *MAM* en.</span><span class="sxs-lookup"><span data-stu-id="99048-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="99048-129">**Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**</span><span class="sxs-lookup"><span data-stu-id="99048-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="99048-130">Abra Outlook 2016 y agregue su Microsoft 365 Business cuenta si es necesario e inicie sesión con sus Microsoft 365 Business credenciales.</span><span class="sxs-lookup"><span data-stu-id="99048-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="99048-131">Abra un correo electrónico y copie parte del contenido de él.</span><span class="sxs-lookup"><span data-stu-id="99048-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="99048-132">Abra el Bloc de notas e intente pegar el contenido.</span><span class="sxs-lookup"><span data-stu-id="99048-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="99048-133">Recibirá un error que indica que la aplicación no puede obtener acceso al contenido.</span><span class="sxs-lookup"><span data-stu-id="99048-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="99048-135">Sin embargo, puede pegar el mismo contenido en Word 2016.</span><span class="sxs-lookup"><span data-stu-id="99048-135">You can, however, paste the same content into Word 2016.</span></span>
    

