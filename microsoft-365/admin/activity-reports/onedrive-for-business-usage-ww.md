---
title: Microsoft 365 OneDrive para la Empresa informes de uso
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
description: 'Obtenga el informe de uso de OneDrive para la Empresa para conocer el número total de archivos y almacenamiento que se usan en toda la organización. '
ms.openlocfilehash: f212a29a5fb41aae9ecb0daeae0638d7af1e5dd1
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781591"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>informes de Microsoft 365 en el centro de administración: uso de OneDrive para la Empresa

En el panel informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, la tarjeta de OneDrive en el panel le ofrece una vista general del valor que obtiene de OneDrive para la Empresa en cuanto al número total de archivos y almacenamiento que se usa en su organización. Después, puede explorarlo en profundidad para comprender las tendencias de las cuentas activas de OneDrive, con cuántos archivos interactúan los usuarios, así como el almacenamiento usado. También le ofrece los detalles de cada usuario de OneDrive.

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Cómo llegar al informe de uso de OneDrive?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la tarjeta OneDrive.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretar el informe de uso de OneDrive

Para ver el uso en el informe de OneDrive, elija la pestaña **Uso**.<br/>![informes de Microsoft 365: informe de uso de Microsoft OneDrive.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![OneDrive informe de uso: elija columnas.](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el vínculo **Exportar**. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 

El informe de **uso de OneDrive para la Empresa** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|URL  <br/> |Dirección web del OneDrive del usuario. <br/> |
|Deleted  <br/> |Estado de eliminación del OneDrive. Pueden pasar al menos 7 días hasta que las cuentas se marquen como eliminadas.  <br/> |
|Owner  <br/> |Nombre de usuario del administrador principal del OneDrive.   <br/> |
|Nombre principal del propietario  <br/> |Dirección de correo electrónico del propietario del OneDrive. <br/> |
|Fecha de la última actividad (UTC)  <br/> | La última fecha en que se realizó una actividad de archivo en el OneDrive. Si la OneDrive no ha tenido actividad de archivos, el valor se mostrará en blanco.  <br/> |
|Archivos  <br/> |Número de archivos de la OneDrive. <br/>|
|Archivos activos  <br/> | Número de archivos activos dentro del período de tiempo.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos de la OneDrive. >  Los usuarios eliminados seguirán apareciendo en los informes de 180 días.  <br/> |
|Storage se usa (MB)  <br/> |Cantidad de almacenamiento que usa el OneDrive en MB. |
|||
   
> [!NOTE]
> El informe solo incluye los usuarios que tienen una licencia de OneDrive para la Empresa válida.
