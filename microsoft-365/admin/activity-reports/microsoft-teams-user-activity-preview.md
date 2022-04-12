---
title: Centro de administración de Microsoft 365 Teams informes de actividad de usuario
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Obtenga información sobre cómo obtener el informe de actividad del usuario Microsoft Teams y obtener información sobre la actividad de Teams en su organización.
ms.openlocfilehash: a5261261a1a1cb7b2039b646c3dbbd92c5f43688
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781663"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Informes de Microsoft 365 en el Centro de administración: actividad de usuario de Microsoft Teams

En el panel informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de actividad de los usuarios de Microsoft Teams puede obtener estadísticas sobre la actividad de Microsoft Teams en su organización.
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Cómo obtener el informe de actividad de los usuarios de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. En la página principal del panel, haga clic en el botón **Ver más** de la tarjeta de actividad Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de los usuarios de Microsoft Teams

Puede ver la actividad del usuario en el informe de Teams eligiendo la pestaña Actividad de **usuario**. <br/>![informes de Microsoft 365: Microsoft Teams actividad del usuario.](../../media/user-activity-charts.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Teams informe de actividad del usuario: elija columnas.](../../media/user-activity-columns.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el vínculo **Exportar**. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. El formato exportado para **el tiempo de audio**, **el tiempo de vídeo** y el **tiempo de uso compartido de pantalla** sigue el formato de duración ISO8601.

Puede visualizar el informe **Actividad de los usuarios en Microsoft Teams** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).

Para garantizar la calidad de los datos, realizamos comprobaciones diarias de validación de datos durante los últimos tres días y rellenaremos las brechas detectadas. Es posible que observe diferencias en los datos históricos durante el proceso.

|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.   <br/> |
|Nombre del inquilino  <br/> |Nombre de un inquilino interno o externo al que pertenece un usuario.   <br/> <br/> Si un usuario pertenece a un inquilino externo, las métricas de datos correspondientes (por ejemplo, mensajes de publicación, mensajes de respuesta, etc.) se calculan en función de sus interacciones en canales compartidos del inquilino del administrador. Las interacciones realizadas por el usuario en su propio inquilino (fuera de los canales compartidos del inquilino determinado) no se tienen en cuenta para el informe de uso del administrador de un inquilino determinado.  |
|Nombres de inquilino de canal compartido   <br/> |Nombres de inquilinos internos o externos de canales compartidos en los que participó el usuario.   <br/> |
|Mensajes del canal   <br/> |Número de mensajes únicos que el usuario publicó en un chat de equipo durante el período de tiempo especificado.  <br/> |
|Posts   <br/> |Número de mensajes de publicación en todos los canales durante el período de tiempo especificado <br/> |
|Responde   <br/> |Número de mensajes respondidos en todos los canales durante el período de tiempo especificado. <br/> |
|Mensajes urgentes    <br/> |Número de mensajes urgentes durante el período de tiempo especificado. <br/> |
|Mensajes de chat   <br/> |Número de mensajes únicos que el usuario publicó en un chat privado durante el período de tiempo especificado.  <br/> |
|Total de reuniones   <br/> |Número de reuniones en línea en las que el usuario participó durante el período de tiempo especificado.  <br/> |
|1:1 llamadas   <br/> | Número de llamadas 1:1 en las que participó el usuario durante el período de tiempo especificado.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |Última fecha en la que el usuario participó en una actividad de Microsoft Teams.<br/> |
|Las reuniones participaron ad hoc   <br/> | Número de reuniones ad hoc en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Reuniones organizadas ad hoc <br/> |Número de reuniones ad hoc organizadas por un usuario durante el período de tiempo especificado. <br/>|
|Total de reuniones organizadas  <br/> |La suma de reuniones programadas, periódicas, ad hoc y sin clasificar organizadas por un usuario durante el período de tiempo especificado.  <br/> |
|Total de reuniones participantes  <br/> |La suma de las reuniones programadas, periódicas, ad hoc y no clasificadas de una sola vez en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Reuniones organizadas programadas una sola vez  <br/> |Número de reuniones programadas de una sola vez organizadas por un usuario durante el período de tiempo especificado.  <br/> |
|Reuniones programadas periódicas organizadas  <br/> |Número de reuniones periódicas organizadas por un usuario durante el período de tiempo especificado.  <br/> |
|Las reuniones participaron programadas una sola vez  <br/> |Número de reuniones programadas únicas en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Las reuniones participaron periódicamente programadas  <br/> |Número de reuniones periódicas en las que participó un usuario durante el período de tiempo especificado.  <br/> |
|Tiene licencia  <br/> |Se selecciona si el usuario tiene licencia para usar Teams. <br/>|
|Otra actividad  <br/>|El usuario está activo, pero ha realizado otras actividades que los tipos de acción expuestos que se ofrecen en el informe (enviar o responder a mensajes de canal y chat, programar o participar en llamadas y reuniones 1:1). Las acciones de ejemplo son cuando un usuario cambia el estado de Teams o el mensaje de estado Teams o abre una publicación de mensaje de canal, pero no responde.  <br/>|
|Reuniones sin clasificar <br/>|El que no se puede clasificar como programa o periódico o ad hoc. Estos son cortos en número y, en su mayoría, no se pueden identificar debido a información de telemetría alterada. |

## <a name="make-the-user-specific-data-anonymous"></a>Hacer anónimos los datos específicos del usuario

Para que los datos de Teams informe de actividad de usuario sean anónimos, debe ser administrador global. Esto ocultará la información de identificación (mediante hashes MD5), como el nombre para mostrar, el correo electrónico y Azure Active Directory id. de objeto en el informe y su exportación.

1. En Centro de administración de Microsoft 365, vaya a la **Configuración Configuración** >  **Org** y, en la pestaña **Servicios**, elija **Informes**.

2. Seleccione **Informes** y, a continuación, elija **Mostrar identificadores anónimos**. Esta configuración se aplica a los informes de uso de Centro de administración de Microsoft 365 y Teams centro de administración.

3. Seleccione **Guardar cambios**.


## <a name="see-also"></a>Vea también
[Informe de uso de dispositivos de Microsoft Teams](../activity-reports/microsoft-teams-device-usage-preview.md)

[Microsoft Teams informe de actividad de uso](../activity-reports/microsoft-teams-usage-activity.md) 
