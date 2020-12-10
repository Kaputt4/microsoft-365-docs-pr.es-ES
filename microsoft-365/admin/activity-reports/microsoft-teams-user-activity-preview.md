---
title: 'Informes de Microsoft 365 en el centro de administración: actividad de los usuarios de Microsoft Teams'
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga información sobre cómo obtener el informe de actividad de los usuarios de Microsoft Teams y obtenga información sobre la actividad de Teams en su organización.
ms.openlocfilehash: 7e32ca6b665cab9da93dec9632ef25176db0e839
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611405"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Informes de Microsoft 365 en el centro de administración: actividad de los usuarios de Microsoft Teams

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de actividad de los usuarios de Microsoft Teams puede obtener estadísticas sobre la actividad de Microsoft Teams en su organización.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Cómo obtener el informe de actividad de los usuarios de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. En la Página principal del panel, haga clic en el botón **Ver más** de la tarjeta de actividad de Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de los usuarios de Microsoft Teams

Puede ver la actividad de usuario en el informe de Microsoft Teams seleccionando la ficha **actividad de usuario** . <br/>![Microsoft 365 Reports: actividad de usuario de Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Seleccione **elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. El formato exportado para **tiempo de audio**, **tiempo de vídeo** y **tiempo de uso compartido de pantalla** sigue el formato de duración ISO8601.

Para garantizar la calidad de los datos, se realizan comprobaciones de validación de datos diarias para los últimos tres días y se rellenarán los huecos detectados. Es posible que observe diferencias en los datos históricos durante el proceso.

|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.   <br/> |
|Mensajes del canal   <br/> |El número de mensajes únicos que el usuario ha publicado en un chat de grupo durante el período de tiempo especificado.  <br/> |
|Mensajes de chat   <br/> |El número de mensajes únicos que el usuario ha publicado en un chat privado durante el período de tiempo especificado.  <br/> |
|Total de reuniones   <br/> |Número de reuniones en línea en las que el usuario participó durante el período de tiempo especificado.  <br/> |
|1:1 llamadas   <br/> | Número de llamadas de 1:1 en las que el usuario participó durante el período de tiempo especificado.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La última fecha en la que el usuario participó en una actividad de Microsoft Teams.<br/> |
|Ad participó de reuniones   <br/> | Número de reuniones no programadas en el calendario en el que el usuario participó durante el período de tiempo especificado.  <br/> |
|Reuniones organizadas por ad hoc <br/> |Número de reuniones no programadas en el calendario que el usuario organizó durante el período de tiempo especificado. <br/>|
|Reuniones organizadas programadas  <br/> |Número de reuniones programadas que un usuario organizó durante el período de tiempo especificado.  <br/> |
|Tiene licencia |Seleccionado si el usuario tiene licencia para usar Teams.|
|Otra actividad|El usuario está activo, pero ha realizado otras actividades que los tipos de acción expuestos que se ofrecen en el informe (envío o respuesta a mensajes de canal y mensajes de chat, programación o participación en llamadas y reuniones de 1:1). Las acciones de ejemplo son cuando un usuario cambia el estado de los equipos o el mensaje de estado de Teams o abre una entrada de mensaje de canal pero no responde. |
|||