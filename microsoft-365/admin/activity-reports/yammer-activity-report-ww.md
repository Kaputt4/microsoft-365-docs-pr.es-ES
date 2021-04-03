---
title: 'Informes de Microsoft 365 en el centro de administración: informe de actividad de Yammer'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtén el informe actividad de Yammer y obtén más información sobre el número de usuarios que usan Yammer para publicar, gustar o leer un mensaje.
ms.openlocfilehash: 636e5fae9a71fc819a032743e06127dace25f0a4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579499"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Informes de Microsoft 365 en el centro de administración: informe de actividad de Yammer

Como administrador de Microsoft 365, el panel **informes** muestra datos sobre el uso de los productos dentro de la organización. Consulte los [informes de actividad en el Centro de administración.](activity-reports.md) Con el **informe de actividad de Yammer**, podrá comprender el nivel de participación de la organización con Yammer consultando el número de usuarios únicos que usan Yammer para publicar, leer o indicar que les gusta un mensaje, y la cantidad de actividad generada en toda la organización. 
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>¿Cómo puedo llegar al informe de actividad de Yammer?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el **botón Ver más** de la tarjeta Yammer.

  
## <a name="interpret-the-yammer-activity-report"></a>Interpretar el informe de actividad de Yammer

Puede ver las actividades en el informe de Yammer seleccionando la **pestaña** Actividad.<br/>![Informes de Microsoft 365: informe de actividad de Microsoft Yammer.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de actividad de Yammer: elegir columnas](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. Esta cuadrícula muestra los usuarios que iniciaron sesión en Yammer con la cuenta de Microsoft 365 o que iniciaron sesión en la red mediante el inicio de sesión único. <br/> |
|Nombre para mostrar  <br/> |Nombre completo del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.  <br/> |
|Estado del usuario  <br/> |Uno de tres valores: Activado, Eliminado o Suspendido. En estos informes se muestran datos para usuarios activos, suspendidos y eliminados. No reflejan usuarios pendientes, porque los usuarios pendientes no publican, leen o indican que les gusta un mensaje.  <br/> |
|Fecha de cambio de estado (UTC)  <br/> |La fecha en la que se cambió el estado del usuario en Yammer.  <br/> |
|Fecha de última actividad (UTC)  <br/> | La última fecha en la que el usuario publicó, leyó o le gustó un mensaje.  <br/> |
|Publicado  <br/> |El número de mensajes que el usuario publicó durante el período de tiempo especificado. <br/>|
|Lectura  <br/> |El número de conversaciones que el usuario leyó durante el período de tiempo especificado.  <br/> |
|Etiquetado como “Me gusta”  <br/> |El número de mensajes que el usuario ha gustado durante el período de tiempo especificado.  <br/>|
|Producto asignado  <br/> |Los productos que se asignan a este usuario.|
|||