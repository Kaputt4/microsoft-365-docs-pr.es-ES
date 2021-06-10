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
# <a name="create-and-edit-autopilot-devices"></a>Crear y editar dispositivos de Autopilot

## <a name="upload-a-list-of-devices"></a>Cargar una lista de dispositivos

Puedes usar la [guía paso a](add-autopilot-devices-and-profile.md) paso para cargar dispositivos, pero también puedes cargar dispositivos en la pestaña **Dispositivos.** 
  
Los dispositivos deben cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior
    
- Nuevos dispositivos que no han pasado por Windows experiencia lista para su uso

1. En el centro Microsoft 365 administración, elija **Dispositivos** \> **AutoPilot**.
  
2. En la **página AutoPilot,** elija la **pestaña Dispositivos** \> **Agregar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. En el **panel Agregar dispositivos,** busque un [archivo CSV de](../admin/misc/device-list.md) lista de dispositivos que preparó \> **Guardar** \> **cerrar**.
    
    Puede obtener esta información del proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Asignar un perfil a un dispositivo o un grupo de dispositivos

1. En la **página Preparar Windows,** elija la pestaña **Dispositivos** y active la casilla junto a uno o varios dispositivos. 
    
2. En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**. 
    
    Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones. 
