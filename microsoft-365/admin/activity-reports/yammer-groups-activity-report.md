---
title: 'Informes de Microsoft 365 en el centro de administración: informe de actividad de grupos de Yammer'
f1.keywords:
- NOCSH
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
- MET150
- MOE150
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: Obtenga el informe de actividad de grupos de Yammer para conocer el número de grupos de Yammer que se crean y usan en su organización, así como su actividad.
ms.openlocfilehash: a8fb1ed4a22420723fa28b7d5a175e2ccf777e77
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948849"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Informes de Microsoft 365 en el centro de administración: informe de actividad de grupos de Yammer

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md). En el informe de actividad de grupos de Yammer puede obtener estadísticas sobre la actividad de grupos de Yammer en su organización y consultar cuántos grupos de Yammer se crean y utilizan.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>Obtener acceso al informe de actividad de grupos de Yammer

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione **Yammer** \> **actividad de grupos**de Yammer.
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Interpretar el informe de actividad de grupos de Yammer

Puede obtener una vista de la actividad de grupos de Yammer consultando los gráficos **Grupos** y **Actividad**.<br/>![Yammer groups activity chart](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|Item|Descripción|
|:-----|:-----|
|1.  <br/> |Puede visualizar el informe **Actividad de grupos de Yammer** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe normalmente cubren hasta las últimas 24 a 48 horas. <br/> |
|3.  <br/> |En la vista **Grupos** se muestra el número total de grupos que ha habido y cuántos llevaron a cabo actividades de conversación en grupo.  <br/> |
|4.  <br/> |En la vista **Actividad** se muestra el número de mensajes de Yammer publicados, leídos y aquellos que las personas han indicado que les gustan en el grupo.  <br/> |
|5.  <br/> | En el gráfico **Grupos**, el eje Y es el número de grupos totales o activos.  <br/>  En el gráfico **Actividad**, el eje Y es el número especificado de actividades para grupos de Yammer.  <br/>  En los tres gráficos, el eje X es el intervalo de fechas seleccionado para el informe específico.  <br/> |
|6.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **grupos** , seleccione los iconos **Active**total o activo total o **Total** ![ activo ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) para ver solo la información relacionada con cada uno de ellos.   Si cambia esta selección, no cambiará la información en la tabla de cuadrícula.  <br/> |
|7.  <br/> | La lista de los grupos que mostrar depende de la configuración de todos los grupos que existieron (y que no se eliminaron) a lo largo del plazo para la creación de informes más extenso (180 días). El recuento de actividades (mensajes recibidos) variará según la selección de fecha.  <br/> Nota: es posible que no vea todos los elementos de la lista siguiente en las columnas hasta que los agregue.<br/>**Nombre del grupo** es el nombre del grupo.  <br/> **Administrador del grupo** es el nombre del administrador o propietario del grupo.  <br/> **Eliminados** es el número de grupos de Yammer eliminados. Si el grupo se elimina, pero tuvo actividad durante el período de presentación de informes, se mostrará en la cuadrícula con esta marca establecida en true.  <br/> **Tipo** es el tipo de grupo: público o privado.  <br/> **Conectado a Office 365** indica si el grupo de Yammer es también un grupo de Microsoft 365.  <br/> **Fecha de la última actividad** es la última fecha en la que el grupo leyó, contabilizó o gustó un mensaje.  <br/> **Miembros** es el número de miembros del grupo.  <br/> **Publicados** es el número de mensajes publicados en el grupo de Yammer durante el período de creación de informes.  <br/> **Leídos** es el número de conversaciones leídas en el grupo de Yammer durante el período de creación de informes.  <br/> **Lo que gusta** es el número de mensajes que han gustado en el grupo de Yammer durante el período de creación de informes.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en [informes de actividad en el centro de administración de Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Seleccione **columnas** para agregar o quitar columnas del informe.  <br/> ![Yammer groups activity - choose columns](../../media/31bd549b-363d-4888-a45d-7af6fedb3588.png)|
|9.  <br/> |También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   

