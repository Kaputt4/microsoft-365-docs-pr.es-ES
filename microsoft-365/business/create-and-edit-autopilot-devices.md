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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Obtenga información acerca de cómo cargar dispositivos con el piloto automático en Microsoft 365 empresa Premium. Puede asignar un perfil a un dispositivo o a un grupo de dispositivos.
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401002"
---
# <a name="create-and-edit-autopilot-devices"></a>Crear y editar dispositivos de Autopilot

## <a name="upload-a-list-of-devices"></a>Cargar una lista de dispositivos

Puede usar la [Guía paso a paso](add-autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargar dispositivos en la pestaña **dispositivos** . 
  
Los dispositivos deben cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior
    
- Nuevos dispositivos que no han estado a la vista rápida de Windows

1. En el centro de administración de Microsoft 365, elija **dispositivos** \> **AutoPilot**.
  
2. En la página **AutoPilot** , elija la pestaña **dispositivos** y \> **agregue dispositivos**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. En el panel **Agregar dispositivos** , vaya a un [archivo CSV](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) de la lista de dispositivos que haya preparado para \> **Guardar** el \> **cierre**.
    
    Puede obtener esta información de su proveedor de hardware o puede usar el script de [PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Asignar un perfil a un dispositivo o un grupo de dispositivos

1. En la página **preparar Windows** , elija la pestaña **dispositivos** y active la casilla junto a uno o más dispositivos. 
    
2. En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**. 
    
    Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones. 
    
