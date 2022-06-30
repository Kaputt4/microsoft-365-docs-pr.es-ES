---
title: Crear y editar dispositivos de Autopilot
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: Obtenga información sobre cómo cargar dispositivos con Autopilot en Microsoft 365 Empresa Premium. Puede asignar un perfil a un dispositivo o un grupo de dispositivos.
ms.openlocfilehash: 994eab29d4b04e2de21d3e42a4abc174270f67f7
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66486570"
---
# <a name="create-and-edit-autopilot-devices"></a>Crear y editar dispositivos de Autopilot

## <a name="upload-a-list-of-devices"></a>Cargar una lista de dispositivos

Puede usar la [Guía paso a paso](m365bp-add-Autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargarlos en la pestaña **Dispositivos**. 
  
Los dispositivos deben cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior
    
- Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.

1. En el Centro de administración de Microsoft 365, seleccione **Dispositivos**\>**Autopilot**.
  
2. En la página **Autopilot**, elija la pestaña **Dispositivos** \> **Agregar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](./../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. En el panel **Agregar dispositivos**, vaya al [Archivo .csv con lista de dispositivos](../admin/misc/device-list.md) que preparó \> seleccione **Guardar** \> **Cerrar**.
    
    Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutopilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutopilotInfo), que generará un archivo CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Asignar un perfil a un dispositivo o un grupo de dispositivos

1. En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** y active la casilla junto a uno o más dispositivos. 
    
2. En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**. 
    
    Si aún no tiene ningún perfil, vea [Crear y editar perfiles de Autopilot](../admin/devices/create-and-edit-Autopilot-profiles.md) para obtener instrucciones. 

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
