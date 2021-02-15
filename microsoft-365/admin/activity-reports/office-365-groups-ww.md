---
title: 'Informes de Microsoft 365 en el Centro de administración: grupos de Microsoft 365'
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
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Obtenga un informe de grupos de Microsoft 365 para conocer los grupos y sus actividades.
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612003"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Informes de Microsoft 365 en el centro de administración: grupos de Microsoft 365

El panel informes  de Microsoft 365 muestra la información general sobre la actividad en todos los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de grupos de Microsoft 365, puede obtener información sobre la actividad de los grupos de su organización y ver cuántos grupos se están creando y utilizando.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.  
  
## <a name="how-to-get-to-the-groups-report"></a>Cómo obtener acceso al informe de grupos

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal  del panel, haga clic en el botón Ver más en los usuarios activos - Aplicaciones de Microsoft 365 o los usuarios activos - Tarjeta de servicios de Microsoft 365 para ir a la página del informe de Office 365.
  
## <a name="interpret-the-groups-report"></a>Interpretar el informe de grupos

Puede ver las activaciones en el informe de Office 365 seleccionando la pestaña **Actividad de** grupos.<br/>![Informes de Microsoft 365: Microsoft Office actividad de grupos de 365.](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de actividad de grupos de Office 365: elegir columnas](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 

|Elemento|Description|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre del grupo  <br/> |Nombre del grupo.  <br/> |
|Deleted  <br/> |El número de grupos eliminados. Si el grupo se elimina, pero tuvo actividad durante el período de presentación de informes, se mostrará en la cuadrícula con esta marca establecida en true.  <br/> |
|Propietario del grupo  <br/> |Nombre del propietario del grupo.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La última fecha en que el grupo recibió un mensaje. Es la última fecha en que hubo actividad en una conversación de correo electrónico, Yammer o el sitio.  <br/> |
|Tipo  <br/> |Tipo de grupo. Puede ser un grupo público o privado.  <br/> |
|Mensajes de correo electrónico recibidos en Exchange  <br/> |El número de mensajes recibidos por el grupo.|
|Correos electrónicos en Exchange (total)  <br/> |El número total de elementos en el buzón del grupo.  <br/> |
|Almacenamiento de buzones usado para Exchange (MB)  <br/> |El almacenamiento usado por el buzón del grupo. <br/>|
|Archivos de SharePoint (total)  <br/> |El número de archivos almacenados en sitios de grupo de SharePoint.  <br/> |
|Archivos de SharePoint (activos)  <br/> |El número de archivos en el sitio de grupo de SharePoint en los que se actuaron (vistos o modificados, sincronizados, compartidos interna o externamente) durante el período de informe.  <br/> |
|Almacenamiento total del sitio usado para SharePoint (MB)  <br/> |La cantidad de almacenamiento en MB usada durante el período de informe.  <br/> |
|Mensajes en Yammer (publicado)  <br/> |El número de mensajes publicados en el grupo de Yammer durante el período de informe.  <br/> |
|Mensajes en Yammer (lectura)  <br/> |El número de conversaciones leen en el grupo de Yammer durante el período de presentación de informes.  <br/> |
|Mensajes en Yammer (me gusta)  <br/> |El número de mensajes que gustaron en el grupo de Yammer durante el período de informe.  <br/> |
|Miembros  <br/> |El número de miembros del grupo.  <br/> |
|Miembros externos |El número de usuarios externos del grupo.|
|||