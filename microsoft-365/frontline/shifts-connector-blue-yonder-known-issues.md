---
title: Conector turnos de Teams para problemas conocidos de Blue Yonder
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Enumera los problemas conocidos al usar el conector Team Shifts para Blue Yonder para integrar Shifts con Blue Yonder Workforce Management.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 3873a6a3d62d7f09aeba55a2680854d45dac56f5
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68234599"
---
# <a name="known-issues-teams-shifts-connector-for-blue-yonder"></a>Problemas conocidos: Conector de turnos de Teams para Blue Yonder

En este artículo se enumeran los problemas [conocidos del conector de turnos de Microsoft Teams para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder).

## <a name="you-can-map-an-instance-to-more-than-one-team-using-powershell-or-microsoft-graph"></a>Puede asignar una instancia a más de un equipo mediante PowerShell o Microsoft Graph

Una instancia de Blue Yonder Workforce Management solo debe asignarse a un equipo en un momento dado en una conexión.

Sin embargo, cuando se usa PowerShell o Microsoft Graph para configurar una conexión, es posible asignar una instancia a más de un equipo. Se recomienda evitar la asignación de una instancia a varios equipos, ya que puede dar lugar a problemas de sincronización y comportamientos inesperados.

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Use el asistente del conector de Turnos para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Uso de PowerShell para conectar Turnos a Workforce Management de Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)
- [Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a Blue Yonder Workforce Management](shifts-connector-blue-yonder-admin-center-manage.md)
- [Usar PowerShell para administrar la conexión de Turnos a Workforce Management de Blue Yonder](shifts-connector-powershell-manage.md)
- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
