---
title: Crear y editar perfiles de AutoPilot
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Obtenga información sobre cómo crear, editar, eliminar o quitar perfiles de AutoPilot. '
ms.openlocfilehash: 8fae8af5e7aa7b866745d0b34a4fe11862de6e9d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287783"
---
# <a name="create-and-edit-autopilot-profiles"></a>Crear y editar perfiles de AutoPilot

## <a name="create-a-profile"></a>Crear un perfil

Un perfil se aplica a un dispositivo o a un grupo de dispositivos.
  
1. En el centro de administración de Microsoft 365 Business, elija **dispositivos** \> **AutoPilot**.
  
2. En la **Página AutoPilot** , elija la **** pestaña \> perfiles **crear perfil**.
    
3. En la página **Crear perfil**, especifique un nombre para el perfil que le ayude a identificarlo, como, por ejemplo, Marketing, active la opción que quiera (para más información, vea [About AutoPilot Profile settings](autopilot-profile-settings.md) [Acerca de la configuración de perfiles de AutoPilot]) y elija **Guardar**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Aplicar el perfil a un dispositivo

Después de crear un perfil, puede aplicarlo a un dispositivo o a un grupo de dispositivos. Puede seleccionar un perfil existente en la [guía paso a paso](add-autopilot-devices-and-profile.md), puede aplicarlo a nuevos dispositivos o puede reemplazar un perfil existente para un dispositivo o grupo de dispositivos. 
  
1. En la página **Preparar Windows**, elija la pestaña **Dispositivos**. 
    
2. Active la casilla situada junto al nombre del dispositivo y, en el panel **Dispositivo**, elija un perfil de la lista desplegable **Perfil asignado** \> **Guardar**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Editar, eliminar o quitar un perfil

Después de asignar un perfil a un dispositivo, puede actualizarlo, aunque ya le haya asignado el dispositivo a un usuario. Cuando el dispositivo se conecta a Internet, descarga la última versión del perfil durante el proceso de configuración. Si el usuario restaura la configuración predeterminada de fábrica de su dispositivo, el dispositivo descargará de nuevo las actualizaciones más recientes para el perfil. 
  
### <a name="edit-a-profile"></a>Editar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Perfiles**. 
    
2. Active la casilla situada junto al nombre del dispositivo y, en el panel **Perfil**, actualice cualquiera de las opciones disponibles \> **Guardar**.
    
    Si hace esto antes de que un usuario conecte el dispositivo a Internet, el perfil se aplica en el proceso de instalación.
    
### <a name="delete-a-profile"></a>Eliminar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Perfiles**. 
    
2. Active la casilla situada junto al nombre del dispositivo y, en el panel **Perfil**, haga clic en **Eliminar perfil** \> **Guardar**.
    
    Al eliminar un perfil, se elimina de un dispositivo o un grupo de dispositivos al que se ha asignado.
    
### <a name="remove-a-profile"></a>Quitar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Dispositivos**. 
    
2. Active la casilla situada junto al nombre del dispositivo y, en el panel **Dispositivo**, elija **Ninguno** de la lista desplegable **Perfil asignado** \> **Guardar**.
    
