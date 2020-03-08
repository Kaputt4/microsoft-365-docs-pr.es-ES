---
title: Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Obtenga información sobre cómo usar Windows AutoPilot para configurar nuevos dispositivos con Windows 10 para su empresa para que estén listos para el uso de los empleados.
ms.openlocfilehash: 3b1cf297914862aaa74fdf9a8bb7290d00f73b1d
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561588"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="f94fb-103">Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f94fb-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="f94fb-104">Puede usar Windows AutoPilot para configurar **nuevos** dispositivos con Windows 10 para su empresa para que estén listos para usarse cuando los entregue a sus empleados.</span><span class="sxs-lookup"><span data-stu-id="f94fb-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="f94fb-105">Requisitos del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f94fb-105">Device requirements</span></span>

<span data-ttu-id="f94fb-106">Los dispositivos deben cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="f94fb-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="f94fb-107">Windows 10, versión 1703 o posterior</span><span class="sxs-lookup"><span data-stu-id="f94fb-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="f94fb-108">Nuevos dispositivos que no han estado a la vista rápida de Windows</span><span class="sxs-lookup"><span data-stu-id="f94fb-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="f94fb-109">Usar la guía de configuración para crear perfiles y dispositivos</span><span class="sxs-lookup"><span data-stu-id="f94fb-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="f94fb-110">[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="f94fb-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="f94fb-111">Si aún no ha creado grupos de dispositivos o perfiles, la mejor forma de empezar es usar la guía paso a paso.</span><span class="sxs-lookup"><span data-stu-id="f94fb-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="f94fb-112">También puede [Agregar dispositivos](create-and-edit-autopilot-devices.md) y [asignarles perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía.</span><span class="sxs-lookup"><span data-stu-id="f94fb-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="f94fb-113">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f94fb-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f94fb-114">En el panel de navegación izquierdo, elija **dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="f94fb-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![En el centro de administración, elija dispositivos y, a continuación, AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="f94fb-116">En la página **AutoPilot** , haga clic o pulse **Guía de inicio**.</span><span class="sxs-lookup"><span data-stu-id="f94fb-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="f94fb-118">En la página **Cargar archivo. csv con la lista de dispositivos** , vaya a la ubicación donde se ha preparado el. Archivo CSV y, a continuación, **abrir** \> **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f94fb-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="f94fb-119">El archivo debe tener tres encabezados:</span><span class="sxs-lookup"><span data-stu-id="f94fb-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="f94fb-120">Columna A: Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f94fb-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="f94fb-121">Columna B: Id. del producto de Windows</span><span class="sxs-lookup"><span data-stu-id="f94fb-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="f94fb-122">Columna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="f94fb-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="f94fb-123">Puede obtener esta información de su proveedor de hardware o puede usar el script de [PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f94fb-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="f94fb-p103">Para más información, vea [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="f94fb-p103">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="f94fb-126">En la página **asignar un perfil** , puede elegir un perfil existente o crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="f94fb-126">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="f94fb-127">Si aún no tiene uno, se le pedirá que cree uno.</span><span class="sxs-lookup"><span data-stu-id="f94fb-127">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="f94fb-128">Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f94fb-128">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="f94fb-129">Las características predeterminadas son necesarias y se establecen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f94fb-129">The default features are required and are set automatically.</span></span> <span data-ttu-id="f94fb-130">Las características predeterminadas son:</span><span class="sxs-lookup"><span data-stu-id="f94fb-130">The default features are:</span></span>
    
    - <span data-ttu-id="f94fb-131">Omitir el registro de Cortana, OneDrive y OEM.</span><span class="sxs-lookup"><span data-stu-id="f94fb-131">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="f94fb-132">Se crea la experiencia de inicio de sesión con la marca de la compañía.</span><span class="sxs-lookup"><span data-stu-id="f94fb-132">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="f94fb-133">Conectar los dispositivos a las cuentas de Azure Active Directory y inscribirlos automáticamente para que los administre Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f94fb-133">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="f94fb-134">Para obtener más información, consulte [acerca de la configuración de perfiles de AutoPilot](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f94fb-134">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="f94fb-135">Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="f94fb-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="f94fb-136">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f94fb-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="f94fb-137">Ya **ha terminado** indica que el perfil que ha creado (o elegido) se aplicará al grupo de dispositivos que ha creado cargando la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f94fb-137">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="f94fb-138">La configuración se aplicará cuando los usuarios del dispositivo inicien sesión a continuación.</span><span class="sxs-lookup"><span data-stu-id="f94fb-138">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="f94fb-139">Elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f94fb-139">Choose **Close**.</span></span>
    
