---
title: Crear y editar dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Aprende a cargar dispositivos con AutoPilot en Microsoft 365 Empresa Premium. Puedes asignar un perfil a un dispositivo o a un grupo de dispositivos.
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578495"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="af831-104">Crear y editar dispositivos de Autopilot</span><span class="sxs-lookup"><span data-stu-id="af831-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="af831-105">Cargar una lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="af831-105">Upload a list of devices</span></span>

<span data-ttu-id="af831-106">Puedes usar la [guía paso a](add-autopilot-devices-and-profile.md) paso para cargar dispositivos, pero también puedes cargar dispositivos en la pestaña **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="af831-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="af831-107">Los dispositivos deben cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="af831-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="af831-108">Windows 10, versión 1703 o posterior</span><span class="sxs-lookup"><span data-stu-id="af831-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="af831-109">Nuevos dispositivos que no han pasado por Windows experiencia lista para su uso</span><span class="sxs-lookup"><span data-stu-id="af831-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="af831-110">En el centro Microsoft 365 administración, elija **Dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="af831-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="af831-111">En la **página AutoPilot,** elija la **pestaña Dispositivos** \> **Agregar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="af831-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="af831-113">En el **panel Agregar dispositivos,** busque un [archivo CSV de](../admin/misc/device-list.md) lista de dispositivos que preparó \> **Guardar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="af831-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="af831-114">Puede obtener esta información del proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="af831-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="af831-115">Asignar un perfil a un dispositivo o un grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="af831-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="af831-116">En la **página Preparar Windows,** elija la pestaña **Dispositivos** y active la casilla junto a uno o varios dispositivos.</span><span class="sxs-lookup"><span data-stu-id="af831-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="af831-117">En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**.</span><span class="sxs-lookup"><span data-stu-id="af831-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="af831-118">Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="af831-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
