---
title: Crear y editar perfiles de AutoPilot
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Obtenga información sobre cómo crear, editar, eliminar o quitar perfiles de AutoPilot.
ms.openlocfilehash: 35967cb1f6e2cdeea9d7c42a529526410fa8b586
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593999"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="b66d3-103">Crear y editar perfiles de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="b66d3-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="b66d3-104">Crear un perfil</span><span class="sxs-lookup"><span data-stu-id="b66d3-104">Create a profile</span></span>

<span data-ttu-id="b66d3-105">Un perfil se aplica a un dispositivo o a un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b66d3-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="b66d3-106">En el centro de administración de Microsoft 365 Business, elija **dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="b66d3-107">En la **Página AutoPilot** , elija la \*\*\*\* pestaña \> perfiles **crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="b66d3-108">En la página **crear perfil** , escriba un nombre para el perfil que le ayude a identificarlo, por ejemplo marketing.</span><span class="sxs-lookup"><span data-stu-id="b66d3-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="b66d3-109">Active la configuración que desee y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="b66d3-110">Para obtener más información acerca de la configuración de perfiles de AutoPilot, consulte [acerca de la configuración de perfiles de AutoPilot](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b66d3-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="b66d3-112">Aplicar el perfil a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="b66d3-112">Apply profile to a device</span></span>

<span data-ttu-id="b66d3-113">Después de crear un perfil, puede aplicarlo a un dispositivo o a un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b66d3-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="b66d3-114">Puede elegir un perfil existente en la [Guía paso a paso](add-autopilot-devices-and-profile.md) y aplicarlo a nuevos dispositivos o reemplazar un perfil existente para un dispositivo o un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b66d3-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="b66d3-115">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="b66d3-116">Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **dispositivo** , elija un perfil de la lista \> desplegable **perfil asignado** para **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="b66d3-118">Editar, eliminar o quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="b66d3-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="b66d3-p103">Después de asignar un perfil a un dispositivo, puede actualizarlo, aunque ya le haya asignado el dispositivo a un usuario. Cuando el dispositivo se conecta a Internet, descarga la última versión del perfil durante el proceso de configuración. Si el usuario restaura la configuración predeterminada de fábrica de su dispositivo, el dispositivo descargará de nuevo las actualizaciones más recientes para el perfil.</span><span class="sxs-lookup"><span data-stu-id="b66d3-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="b66d3-122">Editar un perfil</span><span class="sxs-lookup"><span data-stu-id="b66d3-122">Edit a profile</span></span>

1. <span data-ttu-id="b66d3-123">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="b66d3-124">Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **perfil** , actualice cualquiera de las \> opciones de configuración disponibles **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="b66d3-125">Si hace esto antes de que un usuario conecte el dispositivo a Internet, el perfil se aplica en el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="b66d3-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="b66d3-126">Eliminar un perfil</span><span class="sxs-lookup"><span data-stu-id="b66d3-126">Delete a profile</span></span>

1. <span data-ttu-id="b66d3-127">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="b66d3-128">Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **perfil** , seleccione **eliminar perfil** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="b66d3-129">Al eliminar un perfil, se elimina de un dispositivo o un grupo de dispositivos al que se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="b66d3-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="b66d3-130">Quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="b66d3-130">Remove a profile</span></span>

1. <span data-ttu-id="b66d3-131">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="b66d3-132">Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **dispositivo** , elija **ninguno** en la lista \> desplegable **perfil asignado** para **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b66d3-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
