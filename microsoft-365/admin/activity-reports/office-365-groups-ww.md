---
title: Informes de grupos del Centro de administración de Microsoft 365
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
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
description: Obtenga un informe de grupos de Microsoft 365 para obtener información sobre la actividad de los grupos de su organización y ver cuántos grupos se crean y usan.
ms.openlocfilehash: dc3d05fdad68f18b24dae06021b0cb15306b4338
ms.sourcegitcommit: e6443eb3a4c826792806873428c0c17b59f4fde5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2022
ms.locfileid: "65889244"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Informes de Microsoft 365 en el Centro de administración: grupos de Microsoft 365

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de grupos de Microsoft 365, puede obtener información sobre la actividad de los grupos de su organización y ver cuántos grupos se crean y usan.
  
## <a name="how-to-get-to-the-groups-report"></a>Cómo llegar al informe de grupos

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

2. En la página principal del panel, haga clic en el botón **Ver más** en usuarios activos: Aplicaciones de Microsoft 365 o en la tarjeta Usuarios activos - Servicios de Microsoft 365 para llegar a la página del informe de Office 365.
  
## <a name="interpret-the-groups-report"></a>Interpretación del informe de grupos

Para ver las activaciones en el informe de Office 365, elija la pestaña **Actividad de grupos** .

:::image type="content" alt-text="Informes de Microsoft 365: actividad de grupos de Microsoft Office 365." source="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png" lightbox="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png":::

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.

:::image type="content" alt-text="Informe de actividad de grupos de Office 365: elija columnas." source="../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png":::

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo **Exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para filtrar y ordenar, deberá exportar los datos. 

El informe de **grupos** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).

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
[Informes inteligentes e información en el Centro de cumplimiento de seguridad &](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance) (artículo)\
[Informes de Microsoft 365 en el Centro de administración: usuarios activos](../../admin/activity-reports/active-users-ww.md) (artículo)

