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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Valide la configuración de protección de aplicaciones de Microsoft 365 Empresa Premium en dispositivos Windows 10 y compruebe que los usuarios no puedan copiar datos de la empresa en archivos personales o aplicaciones no administradas.
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403398"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="6a684-103">Validar la configuración de protección de aplicaciones en PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="6a684-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="6a684-104">Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="6a684-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="6a684-105">Después de [configurar directivas de protección de la aplicación](protection-settings-for-windows-10-devices.md), puede tardar unas pocas horas en tener efecto la directiva en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a684-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="6a684-106">Si ha  activado la opción Impedir que los usuarios copien datos de la empresa en archivos personales y obligarles a guardar los archivos de trabajo en la configuración de **OneDrive** para la Empresa para dispositivos propiedad de la empresa, puede comprobarlo en el dispositivo del usuario después de conectarse a Azure AD e haber iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="6a684-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="6a684-107">**Comprobar la configuración de conexión**</span><span class="sxs-lookup"><span data-stu-id="6a684-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="6a684-108">Después de iniciar sesión con las credenciales de Microsoft 365 Empresa Premium y conectarse a Azure AD, tal como se describe en Configurar dispositivos Windows para usuarios de [Microsoft 365 Empresa Premium,](set-up-windows-devices.md)vaya a la escuela o trabajo de Configuración de **Windows.** \>  \> </span><span class="sxs-lookup"><span data-stu-id="6a684-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="6a684-109">Elija **Conectado a Azure \<tenant name\> AD** y, a continuación, elija **Información.**</span><span class="sxs-lookup"><span data-stu-id="6a684-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="6a684-111">En la **página Administrado por,** puedes ver la información de conexión que incluye una dirección del servidor de administración como la que se muestra \<tenant name\> en la ilustración  siguiente. </span><span class="sxs-lookup"><span data-stu-id="6a684-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="6a684-113">**Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**</span><span class="sxs-lookup"><span data-stu-id="6a684-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="6a684-114">Abra Outlook 2016 instalado por Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="6a684-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="6a684-115">Abra un correo electrónico y copie parte del contenido de él.</span><span class="sxs-lookup"><span data-stu-id="6a684-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="6a684-116">Abra el Bloc de notas e intente pegar el contenido.</span><span class="sxs-lookup"><span data-stu-id="6a684-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="6a684-117">Recibirás un error que indica que la aplicación no puede acceder al contenido.</span><span class="sxs-lookup"><span data-stu-id="6a684-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="6a684-119">Sin embargo, puede pegar el mismo contenido en Word 2016.</span><span class="sxs-lookup"><span data-stu-id="6a684-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="6a684-120">Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos personales.</span><span class="sxs-lookup"><span data-stu-id="6a684-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="6a684-121">**Comprobar la configuración de conexión**</span><span class="sxs-lookup"><span data-stu-id="6a684-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="6a684-122">En el dispositivo personal de Windows 10 en el que has iniciado sesión  como usuario local, ve a Configuración de **Windows** y haz clic o pulsa En el acceso a cuentas trabajo \> **o escuela.**</span><span class="sxs-lookup"><span data-stu-id="6a684-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="6a684-123">En **Acceso profesional o educativo**, elija **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="6a684-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="6a684-124">Escribe tu credencial de Microsoft 365 Empresa Premium en el cuadro de diálogo Configurar una cuenta de trabajo o  \> **escuela.**</span><span class="sxs-lookup"><span data-stu-id="6a684-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="6a684-125">En la página **Acceso profesional o educativo**, elija **Cuenta profesional o educativa** y, a continuación, elija **Información**.</span><span class="sxs-lookup"><span data-stu-id="6a684-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Haz clic o pulsa Información en el cuadro de diálogo Cuenta de trabajo o escuela.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="6a684-127">En la página trabajo o escuela  de **Access,**  puedes ver la información de conexión que incluye una dirección del servidor de administración como la que se muestra en la figura siguiente e incluye las palabras *wip* y *mam.*</span><span class="sxs-lookup"><span data-stu-id="6a684-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="6a684-129">**Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**</span><span class="sxs-lookup"><span data-stu-id="6a684-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="6a684-130">Abra Outlook 2016 y agregue su cuenta de Microsoft 365 Empresa Premium si es necesario e inicie sesión con sus credenciales de Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="6a684-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="6a684-131">Abra un correo electrónico y copie parte del contenido de él.</span><span class="sxs-lookup"><span data-stu-id="6a684-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="6a684-132">Abra el Bloc de notas e intente pegar el contenido.</span><span class="sxs-lookup"><span data-stu-id="6a684-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="6a684-133">Recibirá un error que indica que la aplicación no puede acceder al contenido.</span><span class="sxs-lookup"><span data-stu-id="6a684-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="6a684-135">Sin embargo, puede pegar el mismo contenido en Word 2016.</span><span class="sxs-lookup"><span data-stu-id="6a684-135">You can, however, paste the same content into Word 2016.</span></span>
    

