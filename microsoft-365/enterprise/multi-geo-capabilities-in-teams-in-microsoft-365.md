---
title: Capacidades multige geográficas en Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Obtenga información sobre cómo Teams funciona con Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362671"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Capacidades multige geográficas en Microsoft Teams

Las funcionalidades multige geográficas de Teams permiten que Teams datos de chat se almacenen en reposo en una ubicación geográfica especificada. Los datos de chat constan de mensajes de chat, incluidos mensajes privados, mensajes de canal e imágenes usadas en chats.

Teams la ubicación de datos preferida (PDL) para que los usuarios y grupos determinen dónde almacenar los datos. Si la PDL no está establecida o no es válida, los datos se almacenan en la ubicación central del inquilino.

## <a name="user-chat"></a>Chat de usuario

El chat de usuario incluye mensajes de reunión uno a uno, uno a varios y privados.

Cuando se crea un nuevo usuario, Teams lee la PDL del usuario y almacena todos sus datos de chat en esa ubicación geográfica.

Para los usuarios existentes, si un administrador agrega o modifica la PDL de un usuario, los datos de chat de ese usuario se agregan a una cola de migración que se va a mover a la ubicación geográfica especificada.

La ubicación de almacenamiento de un chat de uno a uno o uno a varios se basa en la PDL de la persona que creó el chat. Si se cambia la PDL de ese usuario, el chat se migrará a la nueva ubicación geográfica. La ubicación de almacenamiento de un chat de reunión se basa en la PDL del organizador de la reunión.

Para buscar la ubicación actual de los datos de Teams usuario, conéctese a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) y ejecute el siguiente comando:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Mensajes de canal

Cada Microsoft 365 tiene una ubicación de datos preferida (PDL) que indica la ubicación geográfica donde se almacenarán los datos relacionados. Teams usa la PDL para el grupo asociado a cada equipo para determinar dónde almacenar los datos de mensajería de canal para ese equipo. Esto incluye el chat que se produce dentro de una reunión de canal.

Cuando un usuario crea un nuevo equipo, la PDL de ese usuario determina qué PDL se asigna al grupo Microsoft 365 usuario. La PDL de grupo determina dónde se almacenan los datos de ese equipo. Si la PDL de ese usuario cambia más adelante, no se cambia la PDL del grupo.

En el caso de los equipos existentes, si un administrador agrega o modifica la PDL para el grupo de Microsoft 365 que hace una copia de seguridad de un equipo, los datos de mensajería de canal de ese equipo se agregan a una cola de migración que se va a mover a la ubicación geográfica especificada.

Al cambiar la PDL del grupo de Microsoft 365, se ponen en cola Teams datos para migrar a la ubicación elegida. Sin embargo, esto no migra automáticamente el SharePoint o los archivos asociados con el grupo. Debe mover el sitio por separado siguiendo los procedimientos descritos en [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations). Asegúrese de realizar ambos pasos para evitar los Teams y los SharePoint para un grupo en ubicaciones diferentes.

Para buscar la ubicación actual de los datos de un equipo, conéctese a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) y ejecute el siguiente comando:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Experiencia del usuario

Teams Multi-Geo es perfecto para el usuario final. Una vez que cambie la PDL de un usuario o un grupo, los datos respectivos se pondrán en cola para la migración y la migración se producirá automáticamente sin ningún impacto para el usuario o su cliente de Teams incluso si están activos mientras se produce la migración.

## <a name="see-also"></a>Vea también

[Configuración de inquilino de Microsoft 365 Multi-Geo](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Administración de un entorno multigeográfico](administering-a-multi-geo-environment.md)

[Administración de buzones de correo de Exchange Online en un entorno multigeográfico](administering-exchange-online-multi-geo.md)
