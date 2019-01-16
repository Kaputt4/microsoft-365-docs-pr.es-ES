---
title: Crear y editar dispositivos de AutoPilot
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Obtenga información sobre cómo cargar los dispositivos mediante piloto automático en Microsoft Business de 365. Puede asignar un perfil a un dispositivo o un grupo de dispositivos.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871408"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="5f5fa-104">Crear y editar dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="5f5fa-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="5f5fa-105">Cargar una lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5f5fa-105">Upload a list of devices</span></span>

<span data-ttu-id="5f5fa-106">Puede usar la [Guía paso a paso](add-autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargarlos en la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="5f5fa-107">Los dispositivos tienen que cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="5f5fa-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="5f5fa-108">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="5f5fa-109">Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="5f5fa-110">En el Centro de administración de Microsoft 365 Business, seleccione **Implementar Windows con AutoPilot** en la tarjeta **Acciones de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="5f5fa-112">En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** \> **Agregar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="5f5fa-114">En el panel **Agregar dispositivos** , vaya a una [lista de dispositivos de archivo CSV](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) preparados \> **Guardar** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="5f5fa-115">Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que genera un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="5f5fa-116">Asignar un perfil a un dispositivo o un grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5f5fa-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="5f5fa-117">En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** y active la casilla junto a uno o más dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="5f5fa-118">En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="5f5fa-119">Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5f5fa-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
