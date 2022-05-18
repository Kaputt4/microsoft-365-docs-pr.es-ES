---
title: informes de actividad de Microsoft 365 OneDrive para la Empresa
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el informe de uso OneDrive de su organización y descubra la actividad de cada usuario OneDrive, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: 65046154e17cdb79ee671ec14aa45d089730ca97
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65467260"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>informes de Microsoft 365 en el centro de administración: actividad de OneDrive para la Empresa

En el panel informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle más información pormenorizada acerca de las actividades dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, podrá comprender la actividad de cada usuario con licencia para usar OneDrive consultando su interacción con los archivos en OneDrive. También le ayuda a entender el nivel de colaboración actual observando el número de archivos compartidos.

## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>¿Cómo puedo tener acceso al informe de actividades de OneDrive?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la tarjeta OneDrive.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretar el informe de actividades de OneDrive para la Empresa

Para ver las actividades del informe de OneDrive, elija la pestaña **Actividad**.<br/>![informes de Microsoft 365: informe de actividad de Microsoft OneDrive.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![OneDrive informe de actividad: elija columnas.](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el vínculo **Exportar**. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.

Puede visualizar el informe de **actividad de OneDrive para la Empresa** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |Nombre de usuario del propietario de la cuenta de OneDrive.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La fecha más reciente en la que se realizó una actividad de archivo en la cuenta de OneDrive para el intervalo de fechas seleccionado. . Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> |
|Archivos vistos o editados  <br/> |Número de archivos que el usuario cargó, descargó, modificó o ha visto.   <br/> |
|Archivos sincronizados  <br/> |Número de archivos que se han sincronizado desde el dispositivo local de un usuario con la cuenta de OneDrive. <br/> |
|Archivos compartidos internamente  <br/> | Número de archivos que se han compartido con usuarios de la organización o con usuarios dentro de grupos (que pueden incluir usuarios externos).  <br/> |
|Archivos compartidos externamente  <br/> |Número de archivos que se han compartido con usuarios fuera de la organización. <br/>|
|Deleted  <br/> | Esto indica que se quitó la licencia del usuario.  <br/> NOTA: La actividad de un usuario eliminado seguirá mostrándose en un informe siempre y cuando tenga licencia en algún momento durante el período de tiempo seleccionado. En la columna **Eliminado** puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.  <br/> |
|Fecha de eliminación  <br/> |Fecha en la que se quitó la licencia del usuario. <br/>|
|Producto asignado  <br/> |Los Microsoft 365 productos con licencia para el usuario.|
|||