---
title: Crear y editar dispositivos de AutoPilot
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Obtenga información acerca de cómo cargar dispositivos con el piloto automático en Microsoft 365 empresa Premium. Puede asignar un perfil a un dispositivo o a un grupo de dispositivos.
ms.openlocfilehash: f2a7f801ae471352595a36b355a874b2de653326
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627402"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="f7949-104">Crear y editar dispositivos de Autopilot</span><span class="sxs-lookup"><span data-stu-id="f7949-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="f7949-105">Cargar una lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f7949-105">Upload a list of devices</span></span>

<span data-ttu-id="f7949-106">Puede usar la [Guía paso a paso](add-autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargar dispositivos en la pestaña **dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="f7949-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="f7949-107">Los dispositivos deben cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="f7949-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="f7949-108">Windows 10, versión 1703 o posterior</span><span class="sxs-lookup"><span data-stu-id="f7949-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="f7949-109">Nuevos dispositivos que no han estado a la vista rápida de Windows</span><span class="sxs-lookup"><span data-stu-id="f7949-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="f7949-110">En el centro de administración de Microsoft 365, elija **dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="f7949-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="f7949-111">En la **Página AutoPilot** , elija la **Devices** pestaña \> dispositivos y **agregue dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f7949-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="f7949-113">En el **Panel agregar dispositivos** , vaya a un [archivo CSV](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) de la lista de dispositivos \> que haya preparado para **Guardar** \> el **cierre**.</span><span class="sxs-lookup"><span data-stu-id="f7949-113">On the **Add devices** panel, browse to a [Device list CSV file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="f7949-114">Puede obtener esta información de su proveedor de hardware o puede usar el script de [PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f7949-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="f7949-115">Asignar un perfil a un dispositivo o un grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f7949-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="f7949-116">En la página **preparar Windows** , elija la pestaña **dispositivos** y active la casilla junto a uno o más dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f7949-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="f7949-117">En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**.</span><span class="sxs-lookup"><span data-stu-id="f7949-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="f7949-118">Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f7949-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
