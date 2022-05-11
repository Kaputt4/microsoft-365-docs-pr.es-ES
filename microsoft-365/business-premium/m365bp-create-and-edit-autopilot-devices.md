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
description: Obtenga información sobre cómo cargar dispositivos con AutoPilot en Microsoft 365 Empresa Premium. Puede asignar un perfil a un dispositivo o un grupo de dispositivos.
ms.openlocfilehash: cd5862dab5ff53d52311e7420388cf93b0af63dc
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65317869"
---
# <a name="create-and-edit-autopilot-devices"></a>Crear y editar dispositivos de Autopilot

> [!NOTE]
> Microsoft Defender para Empresas se implementará para los clientes de Microsoft 365 Empresa Premium a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../security/defender-business/mdb-overview.md).

## <a name="upload-a-list-of-devices"></a>Cargar una lista de dispositivos

Puede usar la [Guía paso a paso](m365bp-add-autopilot-devices-and-profile.md) para cargar dispositivos, pero también puede cargarlos en la pestaña **Dispositivos**. 
  
Los dispositivos deben cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior
    
- Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.

1. En el Centro de administración de Microsoft 365, seleccione **Dispositivos**\>**AutoPilot**.
  
2. En la página **AutoPilot**, elija la pestaña **Dispositivos** \> **Agregar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](./../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. En el panel **Agregar dispositivos**, vaya al [Archivo .csv con lista de dispositivos](../admin/misc/device-list.md) que preparó \> seleccione **Guardar** \> **Cerrar**.
    
    Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Asignar un perfil a un dispositivo o un grupo de dispositivos

1. En la página **Preparar Windows**, seleccione la pestaña **Dispositivos** y active la casilla junto a uno o más dispositivos. 
    
2. En el panel **Dispositivo**, seleccione del desplegable **Perfil asignado**. 
    
    Si aún no tiene ningún perfil, vea [Crear y editar perfiles de AutoPilot](../admin/devices/create-and-edit-autopilot-profiles.md) para obtener instrucciones. 

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
