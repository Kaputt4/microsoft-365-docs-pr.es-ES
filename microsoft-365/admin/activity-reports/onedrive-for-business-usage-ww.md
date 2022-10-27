---
title: Informes de uso de Microsoft 365 OneDrive para la Empresa
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
description: Obtenga el informe de uso de OneDrive para la Empresa para obtener más información sobre el número total de archivos y almacenamiento que se usan en toda la organización.
ms.openlocfilehash: ff25945543a7a0bbe7f6fb9c0faf1807edd87522
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722844"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso OneDrive para la Empresa

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md).
  
For example, the OneDrive card on the dashboard gives you a high-level view of the value you are getting from OneDrive for Business in terms of the total number of files and storage used across your organization. You can then drill into it to understand the trends of active OneDrive accounts, how many files are users interacting with as well as the storage used. It also gives you details for each user's OneDrive.

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Cómo llegar al informe de uso de OneDrive?

1. En el centro de administración, vaya a **Informes** y, a continuación, seleccione **Uso**. 
2. En la página principal del panel, haga clic en el botón **Ver más** de la tarjeta de OneDrive.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretar el informe de uso de OneDrive

Para ver el uso en el informe de OneDrive, elija la pestaña **Uso** .

![Informes de Microsoft 365: informe de uso de Microsoft OneDrive.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  

![Informe de uso de OneDrive: elija columnas.](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo **Exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. 

El informe de **uso de OneDrive para la Empresa** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|URL  <br/> |Dirección web de OneDrive del usuario. <br/> |
|Deleted  <br/> |Estado de eliminación de OneDrive. Pueden pasar al menos 7 días hasta que las cuentas se marquen como eliminadas.  <br/> |
|Owner  <br/> |Nombre de usuario del administrador principal de OneDrive.   <br/> |
|Nombre principal del propietario  <br/> |Dirección de correo electrónico del propietario de OneDrive. <br/> |
|Fecha de la última actividad (UTC)  <br/> | La última fecha en que se realizó una actividad de archivo en OneDrive. Si la OneDrive no ha tenido actividad de archivos, el valor se mostrará en blanco.  <br/> |
|Archivos  <br/> |Número de archivos en OneDrive. <br/>|
|Archivos activos  <br/> | Número de archivos activos dentro del período de tiempo.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en OneDrive. >  Los usuarios eliminados seguirán apareciendo en los informes de 180 días.  <br/> |
|Almacenamiento usado (MB)  <br/> |Cantidad de almacenamiento que usa OneDrive en MB. |
|||
   
> [!NOTE]
> El informe solo incluye los usuarios que tienen una licencia de OneDrive para la Empresa válida.
