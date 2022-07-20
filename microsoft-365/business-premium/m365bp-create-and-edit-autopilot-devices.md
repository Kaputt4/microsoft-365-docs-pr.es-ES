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
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo cargar dispositivos con Autopilot en Microsoft 365 Empresa Premium. Puede asignar un perfil a un dispositivo o un grupo de dispositivos.
ms.openlocfilehash: 9e02b985e5742331426210d6d3824dfa120a21d3
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894995"
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
