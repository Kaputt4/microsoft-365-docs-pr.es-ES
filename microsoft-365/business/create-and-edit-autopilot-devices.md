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
# <a name="create-and-edit-autopilot-devices"></a>Crear y editar dispositivos de AutoPilot

## <a name="upload-a-list-of-devices"></a>Cargar una lista de dispositivos

Puede usar la [Guía paso a paso](add-autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargarlos en la pestaña **Dispositivos**. 
  
Los dispositivos tienen que cumplir estos requisitos:
  
- Windows 10, versión 1703 o posteriores.
    
- Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.
    
1. En el Centro de administración de Microsoft 365 Business, seleccione **Implementar Windows con AutoPilot** en la tarjeta **Acciones de dispositivo**. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** \> **Agregar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. En el panel **Agregar dispositivos** , vaya a una [lista de dispositivos de archivo CSV](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) preparados \> **Guardar** \> **Close**.
    
    Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que genera un archivo .csv. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Asignar un perfil a un dispositivo o un grupo de dispositivos

1. En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** y active la casilla junto a uno o más dispositivos. 
    
2. En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**. 
    
    Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](create-and-edit-autopilot-profiles.md) para obtener instrucciones. 
    
