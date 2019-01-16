---
title: Crear y editar perfiles de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Aprenda a crear, editar, eliminar o quitar los perfiles de piloto automático. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871463"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="0ed43-103">Crear y editar perfiles de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="0ed43-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="0ed43-104">Crear un perfil</span><span class="sxs-lookup"><span data-stu-id="0ed43-104">Create a profile</span></span>

<span data-ttu-id="0ed43-105">Un perfil se aplica a un dispositivo o a un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ed43-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="0ed43-106">En el Centro de administración de Microsoft 365 Business, elija **Implementar Windows con AutoPilot** en la tarjeta **Acciones de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-106">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="0ed43-108">En la página **Preparar Windows**, elija la pestaña **Perfiles** \> **Crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-108">On the **Prepare Windows** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="0ed43-109">En la página **Crear perfil**, especifique un nombre para el perfil que le ayude a identificarlo, como, por ejemplo, Marketing, active la opción que quiera (para más información, vea [About AutoPilot Profile settings](autopilot-profile-settings.md) [Acerca de la configuración de perfiles de AutoPilot]) y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-109">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="0ed43-111">Aplicar el perfil a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="0ed43-111">Apply profile to a device</span></span>

<span data-ttu-id="0ed43-p101">Después de crear un perfil, puede aplicarlo a un dispositivo o a un grupo de dispositivos. Puede seleccionar un perfil existente en la [guía paso a paso](add-autopilot-devices-and-profile.md), puede aplicarlo a nuevos dispositivos o puede reemplazar un perfil existente para un dispositivo o grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ed43-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="0ed43-114">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-114">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="0ed43-115">Active la casilla situada junto al nombre del dispositivo y, en el panel **Dispositivo**, elija un perfil de la lista desplegable **Perfil asignado** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-115">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="0ed43-117">Editar, eliminar o quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="0ed43-117">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="0ed43-p102">Después de asignar un perfil a un dispositivo, puede actualizarlo, aunque ya le haya asignado el dispositivo a un usuario. Cuando el dispositivo se conecta a Internet, descarga la última versión del perfil durante el proceso de configuración. Si el usuario restaura la configuración predeterminada de fábrica de su dispositivo, el dispositivo descargará de nuevo las actualizaciones más recientes para el perfil.</span><span class="sxs-lookup"><span data-stu-id="0ed43-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="0ed43-121">Editar un perfil</span><span class="sxs-lookup"><span data-stu-id="0ed43-121">Edit a profile</span></span>

1. <span data-ttu-id="0ed43-122">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-122">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="0ed43-123">Active la casilla situada junto al nombre del dispositivo y, en el panel **Perfil**, actualice cualquiera de las opciones disponibles \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-123">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="0ed43-124">Si hace esto antes de que un usuario conecte el dispositivo a Internet, el perfil se aplica en el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="0ed43-124">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="0ed43-125">Eliminar un perfil</span><span class="sxs-lookup"><span data-stu-id="0ed43-125">Delete a profile</span></span>

1. <span data-ttu-id="0ed43-126">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-126">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="0ed43-127">Active la casilla situada junto al nombre del dispositivo y, en el panel **Perfil**, haga clic en **Eliminar perfil** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-127">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="0ed43-128">Al eliminar un perfil, se elimina de un dispositivo o un grupo de dispositivos al que se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="0ed43-128">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="0ed43-129">Quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="0ed43-129">Remove a profile</span></span>

1. <span data-ttu-id="0ed43-130">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-130">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="0ed43-131">Active la casilla situada junto al nombre del dispositivo y, en el panel **Dispositivo**, elija **Ninguno** de la lista desplegable **Perfil asignado** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ed43-131">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
