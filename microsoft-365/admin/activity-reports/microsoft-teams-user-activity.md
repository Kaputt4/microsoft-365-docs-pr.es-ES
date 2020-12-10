---
title: 'Informes de Microsoft 365 en el centro de administración: actividad de los usuarios de Microsoft Teams'
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Obtenga información sobre cómo obtener el informe de actividad de los usuarios de Microsoft Teams y obtenga información sobre la actividad de Teams en su organización.
ms.openlocfilehash: b2b01371872d0a4b2ebbfb6b011cf8bd4299a90b
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611381"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Informes de Microsoft 365 en el centro de administración: actividad de los usuarios de Microsoft Teams

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de actividad de los usuarios de Microsoft Teams puede obtener estadísticas sobre la actividad de Microsoft Teams en su organización.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Cómo obtener el informe de actividad de los usuarios de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione actividad de usuario de **Microsoft Teams** \> .
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de los usuarios de Microsoft Teams

Puede consultar la actividad de los usuarios en Microsoft Teams mediante los gráficos **Actividad** y **Usuarios**.<br/>![Microsoft 365 Reports: actividad de usuario de Microsoft Teams.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Elemento|Descripción|
|:-----|:-----|
|1.  <br/> |Puede visualizar el informe **Actividad de los usuarios en Microsoft Teams** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe normalmente cubren hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |Para garantizar la calidad de los datos, se realizan comprobaciones de validación de datos diarias durante los últimos cinco días y se rellenarán los huecos detectados. Es posible que observe diferencias en los datos históricos durante el proceso.  <br/> |
|4.  <br/> |La vista **Actividad** muestra el número de actividades de Microsoft Teams por tipo. Los tipos de actividad incluyen los mensajes de chat públicos o privados, las llamadas y las reuniones.  <br/> |
|5.  <br/> |La vista **Usuarios** muestra el número de usuarios por tipo de actividad. Los tipos de actividad incluyen los mensajes de chat públicos o privados, las llamadas y las reuniones.  <br/> |
|6.  <br/> | En el gráfico **actividad** , el eje Y es el recuento de la actividad especificada.  <br/>  En el gráfico **archivos** , el eje Y es el número de usuarios que participan en chats, chats privados, llamadas o reuniones de Microsoft Teams.  <br/>  El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico.  <br/> |
|7.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **actividad** , seleccione **mensajes de canal**, **mensajes de chat**, **llamadas** o **reuniones** para ver solo la información relacionada con cada uno de ellos. Si cambia esta selección, no cambiará la información en la tabla de cuadrícula.  <br/> ![Filtrar los gráficos de actividad de Microsoft Teams](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | La lista de los grupos que se muestra depende de la configuración de todos los grupos que existieron (y que no se eliminaron) a lo largo del plazo para la creación de informes más extenso (180 días). El recuento de actividades variará según la selección de fecha.  <br/> Nota: es posible que no vea todos los elementos de la lista siguiente en las columnas hasta que los agregue.<br/>**Nombre de usuario** es la dirección de correo electrónico de los usuarios. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.  <br/> **Última fecha de actividad (UTC)** hace referencia a la última fecha en la que el usuario haya participado en una actividad de Microsoft Teams.  <br/> **Mensajes de canal** es el número de mensajes únicos que el usuario ha publicado en un chat de grupo durante el período de tiempo especificado.  <br/> **Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en un chat privado durante el período de tiempo especificado.  <br/> **Llamadas** es el número de llamadas en las que el usuario ha participado durante el período de tiempo especificado.  <br/> **Reuniones** es el número de reuniones en línea en las que el usuario ha participado durante el período de tiempo especificado.  <br/> **Otras actividades** es el número de otras actividades de equipo realizadas por el usuario.  <br/> **Eliminar** indica si se eliminará el equipo. Si el equipo se elimina pero ha tenido actividad en el período del informe, se mostrará en la cuadrícula con esta marca establecida en true.  <br/> **Fecha de eliminación** es la fecha de eliminación del equipo.  <br/> **Producto asignado** es la lista de productos asignados al usuario.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en los [informes de actividades del centro de administración de Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Seleccione **columnas** para agregar o quitar columnas del informe.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   

