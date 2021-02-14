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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Aprende a crear un perfil de AutoPilot y aplicarlo a un dispositivo, así como editar o eliminar un perfil o quitar un perfil de un dispositivo.
ms.openlocfilehash: e58418813ed0b4d23a5fa7e1d23aae33d8850e7f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400982"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="aa7dc-103">Crear y editar perfiles de Autopilot</span><span class="sxs-lookup"><span data-stu-id="aa7dc-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="aa7dc-104">Crear un perfil</span><span class="sxs-lookup"><span data-stu-id="aa7dc-104">Create a profile</span></span>

<span data-ttu-id="aa7dc-105">Un perfil se aplica a un dispositivo o a un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="aa7dc-106">En el Centro de administración de Microsoft 365, elija **Dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-106">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="aa7dc-107">En la **página AutoPilot,** elija la pestaña **Perfiles** \> **Crear perfil.**</span><span class="sxs-lookup"><span data-stu-id="aa7dc-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="aa7dc-108">En la **página Crear perfil,** escriba un nombre para el perfil que le ayude a identificarlo, por ejemplo Marketing.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="aa7dc-109">Active la configuración que desee y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="aa7dc-110">Para obtener más información acerca de la configuración de perfil de AutoPilot, consulta [Acerca de la configuración de perfil de AutoPilot.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aa7dc-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="aa7dc-112">Aplicar el perfil a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="aa7dc-112">Apply profile to a device</span></span>

<span data-ttu-id="aa7dc-113">Después de crear un perfil, puedes aplicarlo a un dispositivo o a un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="aa7dc-114">Puedes elegir un perfil [](add-autopilot-devices-and-profile.md) existente en la guía paso a paso y aplicarlo a nuevos dispositivos, o reemplazar un perfil existente para un dispositivo o grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="aa7dc-115">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="aa7dc-116">Active la casilla situada junto a un nombre de dispositivo y, en el **Panel** de dispositivos, elija un perfil de la lista desplegable Perfil asignado  \> **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="aa7dc-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="aa7dc-118">Editar, eliminar o quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="aa7dc-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="aa7dc-p103">Después de asignar un perfil a un dispositivo, puede actualizarlo, aunque ya le haya asignado el dispositivo a un usuario. Cuando el dispositivo se conecta a Internet, descarga la última versión del perfil durante el proceso de configuración. Si el usuario restaura la configuración predeterminada de fábrica de su dispositivo, el dispositivo descargará de nuevo las actualizaciones más recientes para el perfil.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="aa7dc-122">Editar un perfil</span><span class="sxs-lookup"><span data-stu-id="aa7dc-122">Edit a profile</span></span>

1. <span data-ttu-id="aa7dc-123">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="aa7dc-124">Active la casilla situada junto a un nombre de dispositivo y, en el panel **Perfil,** actualice cualquiera de las opciones de configuración \> **disponibles guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="aa7dc-125">Si hace esto antes de que un usuario conecte el dispositivo a Internet, el perfil se aplica en el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="aa7dc-126">Eliminar un perfil</span><span class="sxs-lookup"><span data-stu-id="aa7dc-126">Delete a profile</span></span>

1. <span data-ttu-id="aa7dc-127">En la página **Preparar Windows**, elija la pestaña **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="aa7dc-128">Active la casilla situada junto a un nombre de dispositivo y, en el panel **Perfil,** seleccione **Eliminar perfil** \> **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="aa7dc-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="aa7dc-129">Al eliminar un perfil, se elimina de un dispositivo o un grupo de dispositivos al que se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="aa7dc-130">Quitar un perfil</span><span class="sxs-lookup"><span data-stu-id="aa7dc-130">Remove a profile</span></span>

1. <span data-ttu-id="aa7dc-131">En la página **Preparar Windows**, elija la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="aa7dc-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="aa7dc-132">Active la casilla situada junto a un nombre de  dispositivo  y, en el **Panel** de dispositivos, elija Ninguno en la lista desplegable Perfil asignado \> **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="aa7dc-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
