---
title: Funcionalidades multigeográficas en Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
description: Obtenga información sobre cómo funciona Teams con Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9b00b36fb56259361c2cdf8ee1b7cd020923e7d8
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698339"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Funcionalidades multigeográficas en Microsoft Teams

Las funcionalidades multigeográficas de Teams permiten que los datos de chat de Teams se almacenen en reposo en una ubicación geográfica especificada. Los datos de chat constan de mensajes de chat, incluidos mensajes privados, mensajes de canal e imágenes que se usan en los chats.

Teams usa la ubicación de datos preferida (PDL) para que los usuarios y grupos determinen dónde almacenar los datos. Si la PDL no está establecida o no es válida, los datos se almacenan en la ubicación central del inquilino.

> [!NOTE]
> Las funcionalidades multigeográficas de Teams se implantaron en julio de 2021. Los mensajes de chat y canal se migrarán automáticamente a la ubicación geográfica correcta en los próximos trimestres. Los nuevos cambios de PDL se procesarán después de que el inquilino haya completado la sincronización inicial, y los nuevos cambios de PDL posteriores se pondrán en cola y se procesarán en el orden en que se reciban.

## <a name="user-chat"></a>Chat de usuario

El chat de usuario incluye mensajes de reunión uno a uno, uno a varios y privados.

Cuando se crea un nuevo usuario, Teams lee la PDL del usuario y almacena todos sus datos de chat en esa ubicación geográfica.

En el caso de los usuarios existentes, si un administrador agrega o modifica la PDL de un usuario, los datos de chat de ese usuario se agregan a una cola de migración para moverse a la ubicación geográfica especificada.

La ubicación de almacenamiento de un chat uno a uno o uno a varios se basa en la PDL de la persona que creó el chat. Si se cambia la PDL de ese usuario, el chat se migrará a la nueva ubicación geográfica. La ubicación de almacenamiento de un chat de reunión se basa en la PDL del organizador de la reunión.

Para buscar la ubicación actual de los datos de Teams de un usuario, [conéctese a PowerShell de Teams](/powershell/module/teams/connect-microsoftteams) y ejecute el siguiente comando:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Mensajes del canal

Cada grupo de Microsoft 365 tiene una ubicación de datos preferida (PDL) que indica la ubicación geográfica donde se van a almacenar los datos relacionados. Teams usa la PDL del grupo asociado a cada equipo para determinar dónde almacenar los datos de mensajería de canal para ese equipo. Esto incluye canales privados y chat que se producen dentro de una reunión de canal.

Cuando un usuario crea un nuevo equipo, la PDL de ese usuario determina qué PDL se asigna al grupo de Microsoft 365. La PDL del grupo determina dónde se almacenan los datos de ese equipo. Si la PDL de ese usuario cambia más adelante, no se cambia la PDL del grupo.

En el caso de los equipos existentes, si un administrador agrega o modifica la PDL para el grupo de Microsoft 365 que respalda a un equipo, los datos de mensajería de canal de ese equipo se agregan a una cola de migración para moverse a la ubicación geográfica especificada.

Cambiar la PDL del grupo de Microsoft 365 pone en cola los datos de Teams para migrar a la ubicación elegida. Sin embargo, esto no migra automáticamente el sitio de SharePoint ni los archivos asociados al grupo. Debe mover el sitio por separado siguiendo los procedimientos descritos en [Mover un sitio de SharePoint a otra ubicación geográfica](/microsoft-365/enterprise/move-sharepoint-between-geo-locations). Asegúrese de realizar ambos pasos para evitar los datos de Teams y los datos de SharePoint para un grupo en ubicaciones diferentes.

Para buscar la ubicación actual de los datos de un equipo, [conéctese a PowerShell de Teams](/powershell/module/teams/connect-microsoftteams) y ejecute el siguiente comando:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Experiencia del usuario

Teams Multi-Geo es perfecto para el usuario final. Una vez que cambie la PDL de un usuario o un grupo, los datos respectivos se pondrán en cola para la migración y la migración se producirá automáticamente sin ningún impacto para el usuario o su cliente de Teams, incluso si están activos mientras se produce la migración.

## <a name="see-also"></a>Vea también

[Configuración de inquilino de Microsoft 365 Multi-Geo](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Administración de un entorno multigeográfico](administering-a-multi-geo-environment.md)

[Administración de buzones de correo de Exchange Online en un entorno multigeográfico](administering-exchange-online-multi-geo.md)
