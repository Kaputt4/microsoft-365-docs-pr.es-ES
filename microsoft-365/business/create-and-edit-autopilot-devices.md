---
title: Crear y editar dispositivos de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Obtenga información sobre cómo cargar dispositivos con el piloto automático en Microsoft 365 Business. Puede asignar un perfil a un dispositivo o a un grupo de dispositivos.
ms.openlocfilehash: fff2dbc6af45ef9d4189f23849d638172c19dfb2
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277067"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="8a8e3-104">Crear y editar dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="8a8e3-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="8a8e3-105">Cargar una lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="8a8e3-105">Upload a list of devices</span></span>

<span data-ttu-id="8a8e3-106">Puede usar la [Guía paso a paso](add-autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargarlos en la pestaña **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="8a8e3-107">Los dispositivos tienen que cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="8a8e3-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="8a8e3-108">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="8a8e3-109">Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="8a8e3-110">en Microsoft 365 Business Admin center, elija **dispositivos** \> **autopilot** \> **Add**.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot** \> **Add**.</span></span>
  
2. <span data-ttu-id="8a8e3-111">En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** \> **Agregar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-111">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="8a8e3-113">En el panel **Agregar dispositivos** , vaya a un [archivo CSV de la lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que haya \> preparado para **Guardar** \> el **cierre**.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="8a8e3-114">Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que genera un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="8a8e3-115">Asignar un perfil a un dispositivo o un grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="8a8e3-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="8a8e3-116">En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** y active la casilla junto a uno o más dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="8a8e3-117">En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="8a8e3-118">Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8a8e3-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
