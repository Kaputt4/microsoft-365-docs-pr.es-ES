---
title: Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Aprende a usar Windows AutoPilot para configurar nuevos dispositivos Windows 10 para tu empresa para que estén listos para el uso de los empleados.
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636114"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="c2920-103">Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="c2920-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="c2920-104">Puedes usar Windows AutoPilot para configurar nuevos **dispositivos** Windows 10 para tu empresa para que estén listos para su uso cuando se los des a tus empleados.</span><span class="sxs-lookup"><span data-stu-id="c2920-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="c2920-105">Requisitos del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c2920-105">Device requirements</span></span>

<span data-ttu-id="c2920-106">Los dispositivos deben cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="c2920-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="c2920-107">Windows 10, versión 1703 o posterior</span><span class="sxs-lookup"><span data-stu-id="c2920-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="c2920-108">Nuevos dispositivos que no han pasado por Windows experiencia lista para su uso</span><span class="sxs-lookup"><span data-stu-id="c2920-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="c2920-109">Usar la guía de configuración para crear perfiles y dispositivos</span><span class="sxs-lookup"><span data-stu-id="c2920-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="c2920-110">Si aún no has creado grupos de dispositivos o perfiles, la mejor manera de empezar es usando la guía paso a paso.</span><span class="sxs-lookup"><span data-stu-id="c2920-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="c2920-111">También puedes agregar [dispositivos y](create-and-edit-autopilot-devices.md) [asignarles perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía.</span><span class="sxs-lookup"><span data-stu-id="c2920-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="c2920-112">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="c2920-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c2920-113">En el panel de navegación izquierdo, elija **Dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="c2920-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![En el Centro de administración, elija dispositivos y, a continuación, AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="c2920-115">En la **página AutoPilot,** haga clic o pulse **en Guía de inicio**.</span><span class="sxs-lookup"><span data-stu-id="c2920-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="c2920-117">En la **Upload .csv archivo con lista** de dispositivos, vaya a una ubicación donde tenga el archivo de .CSV preparado y, a continuación, **Abra** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2920-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="c2920-118">El archivo debe tener tres encabezados:</span><span class="sxs-lookup"><span data-stu-id="c2920-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="c2920-119">Columna A: Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c2920-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="c2920-120">Columna B: Id. del producto de Windows</span><span class="sxs-lookup"><span data-stu-id="c2920-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="c2920-121">Columna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="c2920-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="c2920-122">Puede obtener esta información del proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c2920-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="c2920-p103">Para más información, vea [Device list CSV-file](../admin/misc/device-list.md) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="c2920-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c2920-125">Este script usa WMI para recuperar las propiedades necesarias para que un cliente registre un dispositivo con Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="c2920-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="c2920-126">Tenga en cuenta que es normal que el archivo CSV resultante no recopile un valor de id. de producto (PKID) de Windows, ya que esto no es necesario para registrar un dispositivo y PKID siendo NULL en el CSV de salida está totalmente bien.</span><span class="sxs-lookup"><span data-stu-id="c2920-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="c2920-127">Solo se rellenarán el número de serie y el hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="c2920-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="c2920-128">En la **página Asignar un perfil,** puede elegir un perfil existente o crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="c2920-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="c2920-129">Si aún no tiene uno, se le pedirá que cree uno.</span><span class="sxs-lookup"><span data-stu-id="c2920-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="c2920-130">Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c2920-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="c2920-131">Las características predeterminadas son necesarias y se establecen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c2920-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="c2920-132">Las características predeterminadas son:</span><span class="sxs-lookup"><span data-stu-id="c2920-132">The default features are:</span></span>
    
    - <span data-ttu-id="c2920-133">Omita el registro de Cortana, OneDrive y OEM.</span><span class="sxs-lookup"><span data-stu-id="c2920-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="c2920-134">Se crea la experiencia de inicio de sesión con la marca de la compañía.</span><span class="sxs-lookup"><span data-stu-id="c2920-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="c2920-135">Conectar dispositivos para que Azure Active Directory cuentas y las inscriban automáticamente para que las administra Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="c2920-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="c2920-136">Para obtener más información, vea [Acerca de la configuración de perfil de AutoPilot](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c2920-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="c2920-137">Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="c2920-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="c2920-138">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2920-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="c2920-139">**Si has terminado,** indica que el perfil que creaste (o elegiste) se aplicará al grupo de dispositivos que creaste cargando la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c2920-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="c2920-140">La configuración estará en vigor cuando los usuarios del dispositivo inicien sesión a continuación.</span><span class="sxs-lookup"><span data-stu-id="c2920-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="c2920-141">Elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c2920-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="c2920-142">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="c2920-142">Related content</span></span>

<span data-ttu-id="c2920-143">[Acerca de la configuración de perfil de AutoPilot](autopilot-profile-settings.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="c2920-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="c2920-144">[Opciones para proteger los dispositivos y los datos de la aplicación](../admin/devices/choose-device-security.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="c2920-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
