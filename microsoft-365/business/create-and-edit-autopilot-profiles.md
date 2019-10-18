---
title: Crear y editar perfiles de AutoPilot
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
ms.openlocfilehash: 4305340a2fc5df8202cf4d85f9e2541690bf9ed0
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574726"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="4267b-103">Crear y editar perfiles de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="4267b-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="4267b-104">Crear un perfil</span><span class="sxs-lookup"><span data-stu-id="4267b-104">Create a profile</span></span>

<span data-ttu-id="4267b-105">Un perfil se aplica a un dispositivo o a un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4267b-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="4267b-106">En el centro de administración de Microsoft 365 Business, elija **dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="4267b-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="4267b-107">En la **Página AutoPilot** , elija la \*\*\*\* pestaña \> perfiles **crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="4267b-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="4267b-108">En la página **Crear perfil**, especifique un nombre para el perfil que le ayude a identificarlo, como, por ejemplo, Marketing, active la opción que quiera (para más información, vea [About AutoPilot Profile settings](autopilot-profile-settings.md) [Acerca de la configuración de perfiles de AutoPilot]) y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4267b-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="4267b-110">Aplicar el perfil a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="4267b-110">Apply profile to a device</span></span>

<span data-ttu-id="4267b-p101">Después de crear un perfil, puede aplicarlo a un dispositivo o a un grupo de dispositivos. Puede seleccionar un perfil existente en la [guía paso a paso](add-autopilot-devices-and-profile.md), puede aplicarlo a nuevos dispositivos o puede reemplazar un perfil existente para un dispositivo o grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4267b-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="4267b-113">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="4267b-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="4267b-114">Active la casilla situada junto al nombre del dispositivo y, en el panel **Dispositivo**, elija un perfil de la lista desplegable **Perfil asignado** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4267b-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="4267b-116">Editar, eliminar o quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="4267b-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="4267b-p102">Después de asignar un perfil a un dispositivo, puede actualizarlo, aunque ya le haya asignado el dispositivo a un usuario. Cuando el dispositivo se conecta a Internet, descarga la última versión del perfil durante el proceso de configuración. Si el usuario restaura la configuración predeterminada de fábrica de su dispositivo, el dispositivo descargará de nuevo las actualizaciones más recientes para el perfil.</span><span class="sxs-lookup"><span data-stu-id="4267b-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="4267b-120">Editar un perfil</span><span class="sxs-lookup"><span data-stu-id="4267b-120">Edit a profile</span></span>

1. <span data-ttu-id="4267b-121">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="4267b-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="4267b-122">Active la casilla situada junto al nombre del dispositivo y, en el panel **Perfil**, actualice cualquiera de las opciones disponibles \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4267b-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="4267b-123">Si hace esto antes de que un usuario conecte el dispositivo a Internet, el perfil se aplica en el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="4267b-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="4267b-124">Eliminar un perfil</span><span class="sxs-lookup"><span data-stu-id="4267b-124">Delete a profile</span></span>

1. <span data-ttu-id="4267b-125">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="4267b-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="4267b-126">Active la casilla situada junto al nombre del dispositivo y, en el panel **Perfil**, haga clic en **Eliminar perfil** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4267b-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="4267b-127">Al eliminar un perfil, se elimina de un dispositivo o un grupo de dispositivos al que se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="4267b-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="4267b-128">Quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="4267b-128">Remove a profile</span></span>

1. <span data-ttu-id="4267b-129">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="4267b-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="4267b-130">Active la casilla situada junto al nombre del dispositivo y, en el panel **Dispositivo**, elija **Ninguno** de la lista desplegable **Perfil asignado** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4267b-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
