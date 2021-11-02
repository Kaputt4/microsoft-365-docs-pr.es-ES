---
title: 'Microsoft 365 Informes en el Centro de administración: OneDrive para la Empresa de administración'
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
description: 'Obtenga el OneDrive para la Empresa de uso para conocer el número total de archivos y almacenamiento usados en toda la organización. '
ms.openlocfilehash: 2deff1e5438dcc6edbe5f12ecd9f428e0242b93f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648848"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365 Informes en el Centro de administración: OneDrive para la Empresa de administración

El panel Microsoft 365 informes le muestra la introducción a la actividad en todos los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, la tarjeta de OneDrive en el panel le ofrece una vista general del valor que obtiene de OneDrive para la Empresa en cuanto al número total de archivos y almacenamiento que se usa en su organización. Después, puede explorarlo en profundidad para comprender las tendencias de las cuentas activas de OneDrive, con cuántos archivos interactúan los usuarios, así como el almacenamiento usado. También le ofrece los detalles de cada usuario de OneDrive.

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>¿Cómo puedo llegar al informe OneDrive de uso?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la OneDrive panel.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretar el informe de uso de OneDrive

Puede ver el uso en el informe OneDrive selección de la **pestaña** Uso.<br/>![Microsoft 365: Microsoft OneDrive de uso.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![OneDrive de uso: elija columnas.](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 

El **OneDrive para la Empresa de uso** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará datos hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|URL  <br/> |La dirección web del usuario OneDrive. <br/> |
|Deleted  <br/> |El estado de eliminación del OneDrive. Pueden pasar al menos 7 días hasta que las cuentas se marquen como eliminadas.  <br/> |
|Owner  <br/> |Nombre de usuario del administrador principal de la OneDrive.   <br/> |
|Nombre principal del propietario  <br/> |La dirección de correo electrónico del propietario del OneDrive. <br/> |
|Fecha de última actividad (UTC)  <br/> | La última fecha en que se realizó una actividad de archivo en el OneDrive. Si la OneDrive no ha tenido actividad de archivos, el valor se mostrará en blanco.  <br/> |
|Archivos  <br/> |El número de archivos de la OneDrive. <br/>|
|Archivos activos  <br/> | El número de archivos activos dentro del período de tiempo.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos de la OneDrive. >  Los usuarios eliminados seguirán apareciendo en los informes de 180 días.  <br/> |
|Storage usado (MB)  <br/> |La cantidad de almacenamiento que OneDrive usa en MB. |
|||