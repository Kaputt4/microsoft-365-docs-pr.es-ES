---
title: 'Informes de Microsoft 365 en el Centro de administración: actividad de usuario de Microsoft Teams'
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
description: Obtenga información sobre cómo obtener el informe de actividad de usuario de Microsoft Teams y obtener información sobre la actividad de Teams en su organización.
ms.openlocfilehash: e8e4ab6fd78fb290243d8fdc780b5a7a14ca2ee0
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233415"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Informes de Microsoft 365 en el Centro de administración: actividad de usuario de Microsoft Teams

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de actividad de los usuarios de Microsoft Teams puede obtener estadísticas sobre la actividad de Microsoft Teams en su organización.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Cómo obtener el informe de actividad de los usuarios de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. En la página principal del panel, haga clic en el **botón Ver más** en la tarjeta de actividad de Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de los usuarios de Microsoft Teams

Puede ver la actividad de usuario en el informe de Teams seleccionando la **pestaña Actividad de** usuario. <br/>![Informes de Microsoft 365: actividad de usuario de Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. El formato exportado para **el tiempo de audio,** **el tiempo de vídeo** y el tiempo de uso compartido de pantalla sigue **el** formato de duración ISO8601.

Puede visualizar el informe **Actividad de los usuarios en Microsoft Teams** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).

Para garantizar la calidad de los datos, se realizan comprobaciones diarias de validación de datos de los últimos tres días y se rellenarán las diferencias detectadas. Es posible que observe diferencias en los datos históricos durante el proceso.

|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.   <br/> |
|Mensajes de canal   <br/> |El número de mensajes únicos que el usuario publicó en un chat de equipo durante el período de tiempo especificado.  <br/> |
|Mensajes de chat   <br/> |El número de mensajes únicos que el usuario publicó en un chat privado durante el período de tiempo especificado.  <br/> |
|Total de reuniones   <br/> |El número de reuniones en línea en las que participó el usuario durante el período de tiempo especificado.  <br/> |
|1:1 llamadas   <br/> | El número de llamadas de 1:1 en las que participó el usuario durante el período de tiempo especificado.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La última fecha en la que el usuario participó en una actividad de Microsoft Teams.<br/> |
|Reuniones en las que ha participado   <br/> | El número de reuniones no programadas en el calendario en las que participó el usuario durante el período de tiempo especificado.  <br/> |
|Reuniones organizadas <br/> |El número de reuniones no programadas en el calendario que organizó el usuario durante el período de tiempo especificado. <br/>|
|Reuniones organizadas programadas  <br/> |El número de reuniones programadas que organizó un usuario durante el período de tiempo especificado.  <br/> |
|Tiene licencia |Se selecciona si el usuario tiene licencia para usar Teams.|
|Otra actividad|El usuario está activo, pero ha realizado otras actividades que no son los tipos de acciones expuestas que se ofrecen en el informe (enviar o responder a mensajes de canal y mensajes de chat, programar o participar en llamadas y reuniones de 1:1). Algunos ejemplos de acciones son cuando un usuario cambia el estado de Teams o el mensaje de estado de Teams o abre una publicación de mensaje de canal, pero no responde. |
|||