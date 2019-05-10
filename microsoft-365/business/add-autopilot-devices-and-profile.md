---
title: Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Obtenga información sobre cómo usar Windows AutoPilot para configurar nuevos dispositivos con Windows 10 para su empresa.
ms.openlocfilehash: 8c4a14b4b9dcbf7a30c1e6e0bdd53418a1ab8a03
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660695"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="db7cb-103">Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="db7cb-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="db7cb-104">Puede usar Windows AutoPilot para configurar **nuevos** dispositivos con Windows 10 para su empresa para que estén listos para un uso productivo en cuanto los entregue a sus empleados.</span><span class="sxs-lookup"><span data-stu-id="db7cb-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="db7cb-105">Requisitos del dispositivo</span><span class="sxs-lookup"><span data-stu-id="db7cb-105">Device requirements</span></span>

<span data-ttu-id="db7cb-106">Los dispositivos tienen que cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="db7cb-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="db7cb-107">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="db7cb-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="db7cb-108">Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.</span><span class="sxs-lookup"><span data-stu-id="db7cb-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="db7cb-109">Usar la guía de configuración para crear perfiles y dispositivos</span><span class="sxs-lookup"><span data-stu-id="db7cb-109">Use the setup guide to create devices and profiles</span></span>

![Pancarta que apunta a https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="db7cb-111">Si todavía no tiene perfiles ni grupos de dispositivos, la mejor forma de empezar es mediante la guía paso a paso, pero también se pueden [agregar dispositivos](create-and-edit-autopilot-devices.md) y [asignar perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía.</span><span class="sxs-lookup"><span data-stu-id="db7cb-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="db7cb-112">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="db7cb-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="db7cb-113">En el panel de navegación izquierdo, seleccione **dispositivos** \> \*\*\*\* de AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="db7cb-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![En el centro de administración, elija dispositivos y, a continuación, AutoPilot.](media/AutoPilot.png)
  
2. <span data-ttu-id="db7cb-115">En la \*\*\*\* página AutoPilot, haga clic o pulse **Guía de inicio**.</span><span class="sxs-lookup"><span data-stu-id="db7cb-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="db7cb-p101">En la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos), vaya a la ubicación donde tenga el archivo .CSV preparado y haga clic en **Abrir** \> **Siguiente**. El archivo debe tener tres encabezados:</span><span class="sxs-lookup"><span data-stu-id="db7cb-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="db7cb-119">Columna A: Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="db7cb-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="db7cb-120">Columna B: Id. del producto de Windows</span><span class="sxs-lookup"><span data-stu-id="db7cb-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="db7cb-121">Columna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="db7cb-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="db7cb-122">Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="db7cb-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="db7cb-p102">Para más información, vea [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="db7cb-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="db7cb-p103">En la página **Assign a profile** (Asignar un perfil), puede seleccionar un perfil existente o crear uno. Si todavía no tiene ninguno, se le pedirá que cree uno.</span><span class="sxs-lookup"><span data-stu-id="db7cb-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="db7cb-127">Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="db7cb-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="db7cb-p104">Las características predeterminadas son obligatorias y se configurarán automáticamente. Las características predeterminadas son:</span><span class="sxs-lookup"><span data-stu-id="db7cb-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="db7cb-130">Se omite el registro de OEM, OneDrive y Cortana.</span><span class="sxs-lookup"><span data-stu-id="db7cb-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="db7cb-131">Se crea la experiencia de inicio de sesión con la marca de la compañía.</span><span class="sxs-lookup"><span data-stu-id="db7cb-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="db7cb-132">Los dispositivos estarán conectados a cuentas de Azure Active Directory e inscritos automáticamente para que Microsoft 365 Business los administre.</span><span class="sxs-lookup"><span data-stu-id="db7cb-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="db7cb-133">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="db7cb-133">For more information, see</span></span>
    
    <span data-ttu-id="db7cb-134">[Información sobre la configuración de los perfiles de AutoPilot](autopilot-profile-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="db7cb-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="db7cb-135">Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="db7cb-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="db7cb-136">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db7cb-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="db7cb-p105">La página **Ha terminado** indica que el perfil que ha creado (o elegido) se aplicará al grupo de dispositivos que ha creado cargando la lista de dispositivos. Esta configuración estará vigente cuando los usuarios del dispositivo inicien la siguiente sesión. Elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="db7cb-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    