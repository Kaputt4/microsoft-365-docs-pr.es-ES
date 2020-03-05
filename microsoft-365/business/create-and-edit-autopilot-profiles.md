---
title: Crear y editar perfiles de AutoPilot
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Aprenda a crear un perfil de AutoPilot y a aplicarlo a un dispositivo, así como editar o eliminar un perfil o quitar un perfil de un dispositivo.
ms.openlocfilehash: 6a8057969242d839ebbb4cbef8d26dd3f1858c59
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417344"
---
# <a name="create-and-edit-autopilot-profiles"></a>Crear y editar perfiles de Autopilot

## <a name="create-a-profile"></a>Crear un perfil

Un perfil se aplica a un dispositivo o a un grupo de dispositivos.
  
1. En el centro de administración de Microsoft 365 Business, elija **dispositivos** \> **AutoPilot**.
  
2. En la **Página AutoPilot** , elija la **** pestaña \> perfiles **crear perfil**.
    
3. En la página **crear perfil** , escriba un nombre para el perfil que le ayude a identificarlo, por ejemplo marketing. Active la configuración que desee y, a continuación, elija **Guardar**. Para obtener más información acerca de la configuración de perfiles de AutoPilot, consulte [acerca de la configuración de perfiles de AutoPilot](autopilot-profile-settings.md).
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Aplicar el perfil a un dispositivo

Después de crear un perfil, puede aplicarlo a un dispositivo o a un grupo de dispositivos. Puede elegir un perfil existente en la [Guía paso a paso](add-autopilot-devices-and-profile.md) y aplicarlo a nuevos dispositivos o reemplazar un perfil existente para un dispositivo o un grupo de dispositivos. 
  
1. En la página **Preparar Windows**, elija la pestaña **Dispositivos**. 
    
2. Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **dispositivo** , elija un perfil de la lista \> desplegable **perfil asignado** para **Guardar**.
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Editar, eliminar o quitar un perfil

Después de asignar un perfil a un dispositivo, puede actualizarlo, aunque ya le haya asignado el dispositivo a un usuario. Cuando el dispositivo se conecta a Internet, descarga la última versión del perfil durante el proceso de configuración. Si el usuario restaura la configuración predeterminada de fábrica de su dispositivo, el dispositivo descargará de nuevo las actualizaciones más recientes para el perfil. 
  
### <a name="edit-a-profile"></a>Editar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Perfiles**. 
    
2. Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **perfil** , actualice cualquiera de las \> opciones de configuración disponibles **Guardar**.
    
    Si hace esto antes de que un usuario conecte el dispositivo a Internet, el perfil se aplica en el proceso de instalación.
    
### <a name="delete-a-profile"></a>Eliminar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Perfiles**. 
    
2. Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **perfil** , seleccione **eliminar perfil** \> **Guardar**.
    
    Al eliminar un perfil, se elimina de un dispositivo o un grupo de dispositivos al que se ha asignado.
    
### <a name="remove-a-profile"></a>Quitar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Dispositivos**. 
    
2. Active la casilla de verificación situada junto al nombre del dispositivo y, en el panel **dispositivo** , elija **ninguno** en la lista \> desplegable **perfil asignado** para **Guardar**.
    
