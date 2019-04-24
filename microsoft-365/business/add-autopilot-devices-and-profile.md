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
description: Obtenga información sobre cómo usar Windows autoPilot para configurar nuevos dispositivos con Windows 10 para su empresa.
ms.openlocfilehash: e0802ddcc0964d0b8d102f7dbdb9116b33cdcf58
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277164"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="65fa5-103">Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="65fa5-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="65fa5-104">Puede usar Windows AutoPilot para configurar nuevos dispositivos de Windows 10 en su empresa para que estén listos para su uso productivo en cuanto se los proporcione a sus empleados.</span><span class="sxs-lookup"><span data-stu-id="65fa5-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="65fa5-105">Requisitos del dispositivo</span><span class="sxs-lookup"><span data-stu-id="65fa5-105">Device requirements</span></span>

<span data-ttu-id="65fa5-106">Los dispositivos tienen que cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="65fa5-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="65fa5-107">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="65fa5-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="65fa5-108">Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.</span><span class="sxs-lookup"><span data-stu-id="65fa5-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="65fa5-109">Usar la guía de configuración para crear perfiles y dispositivos</span><span class="sxs-lookup"><span data-stu-id="65fa5-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="65fa5-110">Si todavía no tiene perfiles ni grupos de dispositivos, la mejor forma de empezar es mediante la guía paso a paso, pero también se pueden [agregar dispositivos](create-and-edit-autopilot-devices.md) y [asignar perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía.</span><span class="sxs-lookup"><span data-stu-id="65fa5-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="65fa5-111">En el Centro de administración de Microsoft 365 Business, busque la tarjeta **Acciones de dispositivo** y elija **Implementar Windows con AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="65fa5-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="65fa5-113">En la página **Preparar Windows**, pulse o haga clic en **Guía de inicio**.</span><span class="sxs-lookup"><span data-stu-id="65fa5-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="65fa5-p101">En la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos), vaya a la ubicación donde tenga el archivo .CSV preparado y haga clic en **Abrir** \> **Siguiente**. El archivo debe tener tres encabezados:</span><span class="sxs-lookup"><span data-stu-id="65fa5-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="65fa5-117">Columna A: Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="65fa5-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="65fa5-118">Columna B: Id. del producto de Windows</span><span class="sxs-lookup"><span data-stu-id="65fa5-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="65fa5-119">Columna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="65fa5-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="65fa5-120">Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="65fa5-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="65fa5-p102">Para más información, vea [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="65fa5-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="65fa5-p103">En la página **Assign a profile** (Asignar un perfil), puede seleccionar un perfil existente o crear uno. Si todavía no tiene ninguno, se le pedirá que cree uno.</span><span class="sxs-lookup"><span data-stu-id="65fa5-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="65fa5-125">Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="65fa5-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="65fa5-p104">Las características predeterminadas son obligatorias y se configurarán automáticamente. Las características predeterminadas son:</span><span class="sxs-lookup"><span data-stu-id="65fa5-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="65fa5-128">Se omite el registro de OEM, OneDrive y Cortana.</span><span class="sxs-lookup"><span data-stu-id="65fa5-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="65fa5-129">Se crea la experiencia de inicio de sesión con la marca de la compañía.</span><span class="sxs-lookup"><span data-stu-id="65fa5-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="65fa5-130">Los dispositivos estarán conectados a cuentas de Azure Active Directory e inscritos automáticamente para que Microsoft 365 Business los administre.</span><span class="sxs-lookup"><span data-stu-id="65fa5-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="65fa5-131">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="65fa5-131">For more information, see</span></span>
    
    <span data-ttu-id="65fa5-132">[Información sobre la configuración de los perfiles de AutoPilot](autopilot-profile-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="65fa5-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="65fa5-133">Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="65fa5-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="65fa5-134">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="65fa5-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="65fa5-p105">La página **Ha terminado** indica que el perfil que ha creado (o elegido) se aplicará al grupo de dispositivos que ha creado cargando la lista de dispositivos. Esta configuración estará vigente cuando los usuarios del dispositivo inicien la siguiente sesión. Elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="65fa5-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    