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
ms.openlocfilehash: 8ce29b43e6238883470d1159ad1d22fefca88792
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637072"
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

También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. El formato exportado para el tiempo de **audio**, la **hora de vídeo** y el **tiempo de uso compartido de pantalla** sigue el formato de duración ISO8601.

|Item|Descripción|
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
|Otra actividad|el usuario se considera activo pero tiene un valor de cero para los mensajes de chat, llamadas de 1:1, mensajes de canal, reuniones totales y reuniones organizadas de valores métricos. Las acciones de ejemplo son cuando un usuario abre una entrada de mensaje de canal, pero no responde o cuando se recibe un mensaje privado y se lee pero no responde. |
|||