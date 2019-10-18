---
title: Crear y editar dispositivos de AutoPilot
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
description: Obtenga información sobre cómo cargar dispositivos con el piloto automático en Microsoft 365 Business. Puede asignar un perfil a un dispositivo o a un grupo de dispositivos.
ms.openlocfilehash: 4eadaa800aa174bcd9cac50375f68c8471e1684e
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575416"
---
# <a name="create-and-edit-autopilot-devices"></a>Crear y editar dispositivos de AutoPilot

## <a name="upload-a-list-of-devices"></a>Cargar una lista de dispositivos

Puede usar la [Guía paso a paso](add-autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargarlos en la pestaña **Dispositivos**. 
  
Los dispositivos tienen que cumplir estos requisitos:
  
- Windows 10, versión 1703 o posteriores.
    
- Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.

1. En el centro de administración de Microsoft 365 Business, elija **dispositivos** \> **AutoPilot**.
  
2. En la **Página AutoPilot** , elija la **** pestaña \> dispositivos y **agregue dispositivos**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. En el panel **Agregar dispositivos** , vaya a un [archivo CSV de la lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que haya \> preparado para **Guardar** \> el **cierre**.
    
    Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que genera un archivo .csv. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Asignar un perfil a un dispositivo o un grupo de dispositivos

1. En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** y active la casilla junto a uno o más dispositivos. 
    
2. En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**. 
    
    Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones. 
    
