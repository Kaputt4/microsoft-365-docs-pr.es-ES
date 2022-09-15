---
title: Crear y editar perfiles de AutoPilot
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: business-premium
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Aprenda a crear un perfil de AutoPilot y aplicarlo a un dispositivo, así como a editar o eliminar un perfil o quitar un perfil de un dispositivo.
ms.openlocfilehash: 2a74bf007f0dcac400033248813afe9558f0b2f8
ms.sourcegitcommit: db89873e22a12705ed313964c1bc2fa19d4fe719
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67712637"
---
# <a name="create-and-edit-autopilot-profiles"></a>Crear y editar perfiles de AutoPilot

Puede aplicar un [perfil de implementación de Windows Autopilot](/mem/autopilot/profiles) a los dispositivos que se encuentren en un [grupo de dispositivos](m365bp-device-groups-mdb.md). Los perfiles de implementación determinan la experiencia de implementación e inscripción de Windows que tendrán los usuarios. 

## <a name="create-a-profile"></a>Crear un perfil

Un perfil se aplica a un dispositivo o a un grupo de dispositivos.
  
1. En el Centro de administración de Microsoft 365, seleccione **Dispositivos** \> **AutoPilot**.
  
2. En la página **AutoPilot**, elija la pestaña **Perfiles** \> **Crear perfil**.

3. En la página **Crear perfil**, especifique un nombre para el perfil que le ayude a identificarlo, como por ejemplo, Marketing. Active la configuración que desee y, a continuación, elija **Guardar**. Para obtener más información sobre la configuración de perfiles de Autopilot, consulte [Acerca de la configuración de perfiles de Autopilot](m365bp-Autopilot-profile-settings.md).

    ![Enter name and turn on settings in the Create profile panel.](./../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Aplicar el perfil a un dispositivo

Después de crear un perfil, puede aplicarlo a un dispositivo o a un grupo de dispositivos. Puede elegir un perfil ya existente en la [guía paso a paso](m365bp-add-Autopilot-devices-and-profile.md) y aplicarlo a nuevos dispositivos, o reemplazar un perfil ya existente para un dispositivo o grupo de dispositivos.
  
1. En la página **Preparar Windows**, elija la pestaña **Dispositivos**.

2. Active la casilla situada junto a un nombre de dispositivo y, en el panel **Dispositivo**, elija un perfil en la lista desplegable **Perfil asignado**\>**Guardar**.

    ![In the Device panel, select an Assigned profile to apply it.](./../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Editar, eliminar o quitar un perfil

Después de asignar un perfil a un dispositivo, puede actualizarlo, aunque ya le haya asignado el dispositivo a un usuario. Cuando el dispositivo se conecta a Internet, descarga la última versión del perfil durante el proceso de configuración. Si el usuario restaura la configuración predeterminada de fábrica de su dispositivo, el dispositivo descargará de nuevo las actualizaciones más recientes para el perfil.
  
### <a name="edit-a-profile"></a>Editar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Perfiles**.

2. Active la casilla situada junto a un nombre de dispositivo y, en el panel **Perfil**, actualice cualquiera de las opciones disponibles \>**Guardar**.

    Si realiza esta tarea antes de que un usuario conecte el dispositivo a Internet, el perfil se aplica en el proceso de instalación.

### <a name="delete-a-profile"></a>Eliminar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Perfiles**.

2. Active la casilla situada junto a un nombre de dispositivo y, en el panel **Perfil**, seleccione **Eliminar perfil**\>**Guardar**.

    Al eliminar un perfil, se elimina de un dispositivo o un grupo de dispositivos al que se ha asignado.

### <a name="remove-a-profile"></a>Quitar un perfil

1. En la página **Preparar Windows**, elija la pestaña **Dispositivos**.

2. Active la casilla situada junto al nombre de un dispositivo y, en el panel **Dispositivo**, elija **Ninguno** en la lista desplegable **Perfil asignado**\>**Guardar**.

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
