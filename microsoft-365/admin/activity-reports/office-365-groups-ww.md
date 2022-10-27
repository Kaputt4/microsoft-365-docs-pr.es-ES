---
title: informes de grupos de Centro de administración de Microsoft 365
ms.author: camillepack
author: camillepack
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Obtenga un informe de Grupos de Microsoft 365 para obtener información sobre la actividad de los grupos de su organización y ver cuántos grupos se crean y usan.
ms.openlocfilehash: 814d1ca174024c06cff20c36d05d886178035cbc
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722866"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Informes de Microsoft 365 en el Centro de administración: grupos de Microsoft 365

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de grupos de Microsoft 365, puede obtener información sobre la actividad de los grupos de su organización y ver cuántos grupos se crean y usan.

## <a name="how-to-get-to-the-groups-report"></a>Cómo llegar al informe de grupos

1. En el centro de administración, seleccione **Informes** y, a continuación, seleccione **Uso**.

2. En la página principal del panel, haga clic en el botón **Ver más** en la tarjeta Usuarios activos Aplicaciones Microsoft 365 o Usuarios activos - Servicios de Microsoft 365 para acceder a la página del informe de Office 365.

## <a name="interpret-the-groups-report"></a>Interpretación del informe de grupos

Para ver las activaciones en el informe de Office 365, elija la pestaña **Actividad de grupos**.

:::image type="content" alt-text="Informes de Microsoft 365: actividad de grupos Microsoft Office 365." source="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png" lightbox="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png":::

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.

:::image type="content" alt-text="Office 365 informe de actividad de grupos: elija columnas." source="../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png":::

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo **Exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. 

El informe de **grupos** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).

### <a name="groupid-hidden-by-default"></a>GroupID oculto de forma predeterminada
Al exportar los datos del informe, de forma predeterminada no podrá ver la variable **GroupID** en el archivo .csv de Excel que descargue. Si desea ver la información de GroupID y toda la información de identificación en los informes de uso de Microsoft 365, puede usar la opción de [mostrar los detalles del usuario en los informes](../../admin/activity-reports/activity-reports.md#show-user-details-in-the-reports) a través de la configuración de la organización en el Centro de administración de Microsoft 365.  Debe ser administrador global para realizar estos cambios.

A continuación se muestran las definiciones de las métricas disponibles en la tabla de informes.

|Métrica|Definición|
|:-----|:-----|
|Nombre del grupo |Nombre del grupo. |
|Deleted |Número de grupos eliminados. Si el grupo se elimina, pero tuvo actividad durante el período de presentación de informes, se mostrará en la cuadrícula con esta marca establecida en true. |
|Propietario del grupo |Nombre del propietario del grupo. |
|Fecha de la última actividad (UTC) |La última fecha en que el grupo recibió un mensaje. Es la última fecha en que hubo actividad en una conversación de correo electrónico, Yammer o el sitio. |
|Tipo |Tipo de grupo. Puede ser un grupo público o privado. |
|Correos electrónicos recibidos en Exchange |Número de mensajes recibidos por el grupo.|
|Correos electrónicos en Exchange (total) |Número total de elementos en el buzón del grupo. |
|Almacenamiento de buzón de correo usado para Exchange (MB) |El almacenamiento usado por el buzón del grupo. |
|Archivos de SharePoint (total) |Número de archivos almacenados en sitios de grupo de SharePoint. |
|Archivos de SharePoint (activos) |Número de archivos del sitio de grupo de SharePoint en los que se actuó (vistos o modificados, sincronizados, compartidos interna o externamente) durante el período de informes. |
|Almacenamiento de sitio total usado para SharePoint (MB) |Cantidad de almacenamiento en MB utilizada durante el período de informes. |
|Mensajes en Yammer (publicados) |Número de mensajes publicados en el grupo de Yammer durante el período de informes. |
|Mensajes en Yammer (lectura) |Número de conversaciones leídas en el grupo de Yammer durante el período de informes. |
|Mensajes en Yammer (me gusta) |El número de mensajes que se han gustado en el grupo de Yammer durante el período de informes. |
|Members |Número de miembros del grupo. |
|Miembros externos |Número de usuarios externos en el grupo.|
|Total de reuniones organizadas  |La suma de las reuniones programadas y periódicas de una sola vez organizadas por un usuario durante el período de tiempo especificado.|
|Mensajes del canal  |Número de mensajes únicos que un usuario publicó en un chat de equipo durante el período de tiempo especificado. Esto incluye entradas y respuestas originales. |

## <a name="related-content"></a>Contenido relacionado

[Informes de Microsoft 365 en el Centro de administración](activity-reports.md) (artículo)\
[Informes de Microsoft 365 en el Centro de administración: usuarios activos](../../admin/activity-reports/active-users-ww.md) (artículo)
