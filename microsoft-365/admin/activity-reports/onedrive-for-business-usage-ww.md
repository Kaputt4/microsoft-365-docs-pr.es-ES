---
title: 'Informes de Microsoft 365 en el centro de administración: uso de OneDrive para la empresa'
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 'Obtenga el informe de uso de OneDrive para la empresa para conocer el número total de archivos y almacenamiento que se usan en la organización. '
ms.openlocfilehash: 3855c7d06d202ee4d0590fcf5b8ca758d8120133
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649864"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Informes de Microsoft 365 en el centro de administración: uso de OneDrive para la empresa

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, la tarjeta de OneDrive en el panel le ofrece una vista general del valor que obtiene de OneDrive para la Empresa en cuanto al número total de archivos y almacenamiento que se usa en su organización. Después, puede explorarlo en profundidad para comprender las tendencias de las cuentas activas de OneDrive, con cuántos archivos interactúan los usuarios, así como el almacenamiento usado. También le ofrece los detalles de cada usuario de OneDrive.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>¿Cómo puedo tener acceso al informe de actividades de OneDrive?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la Página principal del panel, haga clic en el botón **Ver más** de la tarjeta de OneDrive.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretar el informe de uso de OneDrive

Puede ver el uso en el informe de OneDrive eligiendo la pestaña **uso** .<br/>![Informes de Microsoft 365: informe de uso de OneDrive de Microsoft.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Seleccione **elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de uso de OneDrive: elegir columnas](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|URL  <br/> |La dirección web del OneDrive del usuario. <br/> |
|Deleted  <br/> |El estado de eliminación de OneDrive. Pueden pasar al menos 7 días hasta que las cuentas se marquen como eliminadas.  <br/> |
|Owner  <br/> |El nombre de usuario del administrador principal de OneDrive.   <br/> |
|Nombre principal del propietario  <br/> |La dirección de correo electrónico del propietario de OneDrive. <br/> |
|Fecha de la última actividad (UTC)  <br/> | La última fecha en que se realizó una actividad de archivo en OneDrive. Si la OneDrive no ha tenido actividad de archivos, el valor se mostrará en blanco.  <br/> |
|Archivos  <br/> |El número de archivos en el OneDrive. <br/>|
|Archivos activos  <br/> | El número de archivos activos en el período de tiempo.<br/> Nota: si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en OneDrive. >  Los usuarios eliminados seguirán apareciendo en los informes de 180 días.  <br/> |
|Almacenamiento usado (MB)  <br/> |La cantidad de almacenamiento que usa OneDrive en MB. |
|||