---
title: 'Informes de Microsoft 365 en el centro de administración: actividad de usuario de Microsoft Teams'
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: a4f8cd995d1559da3846fbb38cc5a9441358da72
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579619"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Informes de Microsoft 365 en el centro de administración: actividad de usuario de Microsoft Teams

El panel informes  de Microsoft 365 muestra la introducción a la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de actividad de los usuarios de Microsoft Teams puede obtener estadísticas sobre la actividad de Microsoft Teams en su organización.
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Cómo obtener el informe de actividad de los usuarios de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. En la página principal del panel, haga clic en el **botón Ver más** de la tarjeta de actividad de Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de los usuarios de Microsoft Teams

Puede ver la actividad del usuario en el informe de Teams seleccionando la **pestaña Actividad de** usuario. <br/>![Informes de Microsoft 365: actividad de usuario de Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Teams user activity report - choose columns](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. El formato exportado para **tiempo de audio,** **tiempo de vídeo** y tiempo de uso compartido de pantalla sigue el formato de duración ISO8601. 

Puede visualizar el informe **Actividad de los usuarios en Microsoft Teams** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).

Para garantizar la calidad de los datos, llevamos a cabo comprobaciones diarias de validación de datos durante los últimos tres días y se rellenarán los vacíos detectados. Es posible que observe diferencias en los datos históricos durante el proceso.

|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.   <br/> |
|Mensajes de canal   <br/> |Número de mensajes únicos que el usuario publicó en un chat de grupo durante el período de tiempo especificado.  <br/> |
|Mensajes de chat   <br/> |El número de mensajes únicos que el usuario publicó en un chat privado durante el período de tiempo especificado.  <br/> |
|Total de reuniones   <br/> |Número de reuniones en línea en las que el usuario participó durante el período de tiempo especificado.  <br/> |
|Llamadas 1:1   <br/> | Número de llamadas 1:1 en las que el usuario participó durante el período de tiempo especificado.  <br/> |
|Fecha de última actividad (UTC)  <br/> |La última fecha en la que el usuario participó en una actividad de Microsoft Teams.<br/> |
|Reuniones que han participado ad hoc   <br/> | El número de reuniones ad hoc en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Reuniones organizadas ad hoc <br/> |Número de reuniones ad hoc que organizó un usuario durante el período de tiempo especificado. <br/>|
|Total de reuniones organizadas  <br/> |La suma de reuniones programadas únicas, periódicas, ad hoc y sin clasificar que organizó un usuario durante el período de tiempo especificado.  <br/> |
|Total de reuniones participadas  <br/> |La suma de las reuniones programadas, periódicas, ad hoc y sin clasificar únicas en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Reuniones organizadas de una sola vez  <br/> |Número de reuniones programadas de una sola vez que un usuario organizó durante el período de tiempo especificado.  <br/> |
|Reuniones programadas periódicas  <br/> |Número de reuniones periódicas que organizó un usuario durante el período de tiempo especificado.  <br/> |
|Las reuniones participaron una sola vez  <br/> |El número de reuniones programadas únicas en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Reuniones participadas periódicamente programadas  <br/> |Número de reuniones periódicas en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Tiene licencia  <br/> |Se selecciona si el usuario tiene licencia para usar Teams. <br/>|
|Otra actividad  <br/>|El usuario está activo, pero ha realizado otras actividades que no son los tipos de acción expuestos ofrecidos en el informe (enviar o responder a mensajes de canal y mensajes de chat, programar o participar en llamadas y reuniones 1:1). Las acciones de ejemplo son cuando un usuario cambia el estado de Teams o el mensaje de estado de Teams o abre una publicación de mensaje de canal, pero no responde.  <br/>|
|reuniones sin clasificar <br/>|La que no se puede clasificar como programación, periódica o ad hoc. Son números cortos y, en su mayoría, no se pueden identificar debido a la información de telemetría manipulada. |
|||