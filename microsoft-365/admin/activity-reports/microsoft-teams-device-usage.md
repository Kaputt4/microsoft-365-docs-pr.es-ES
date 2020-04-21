---
title: 'Informes de Microsoft 365 en el centro de administración: uso de dispositivos de Microsoft Teams'
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Obtenga información sobre las aplicaciones de Microsoft Teams usadas en su organización al obtener el informe de uso de aplicaciones de Microsoft Teams de los informes de Microsoft 365.
ms.openlocfilehash: 9c79f83d90905470c56fd62489f1439b3383841f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621215"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Informes de Microsoft 365 en el centro de administración: uso de dispositivos de Microsoft Teams

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de uso de aplicaciones de Microsoft Teams puede obtener estadísticas sobre las aplicaciones de Microsoft Teams que se usan en su organización.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Cómo obtener el informe de uso de aplicaciones de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione **uso de dispositivos**de **Microsoft Teams** \> .
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretar el informe de uso de aplicaciones de Microsoft Teams

Para obtener información sobre el uso de aplicaciones de Microsoft Teams, consulte los gráficos **Usuarios** y **Distribución**. 
  
![Informes de Microsoft 365: uso de aplicaciones de Microsoft Teams](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |Puede visualizar el informe **Uso de dispositivos de Microsoft Teams** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe normalmente cubren hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **Usuarios** muestra el número de usuarios únicos diario por aplicación.  <br/> |
|4.  <br/> |La vista **Distribución** muestra el número de usuarios únicos por aplicación durante el período de tiempo seleccionado.  <br/> |
|5.  <br/> | En el gráfico **Usuarios**, el eje Y es el número de usuarios por aplicación.  <br/>  En el gráfico **Distribución**, el eje Y es el número de usuarios que usa la aplicación especificada.  <br/>  En los dos gráficos, el eje X es el intervalo de fechas seleccionado para el informe específico.  <br/> |
|6.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **usuarios** , seleccione **Windows**, **Mac**, **calls**, **Web**, **Android Phone**o **Windows Phone** para ver solo la información relacionada con cada uno de ellos. Si cambia esta selección, no cambiará la información en la tabla de cuadrícula.  <br/> ![Puede filtrar los gráficos de uso de aplicaciones de Microsoft Teams seleccionando el tipo de aplicación.](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | La lista de los grupos que se muestra depende de la configuración de todos los grupos que existieron (y que no se eliminaron) a lo largo del plazo para la creación de informes más extenso (180 días). El recuento de actividades variará según la selección de fecha.  <br/> Nota: es posible que no vea todos los elementos de la lista siguiente en las columnas hasta que los agregue.<br/> **Nombre de usuario** es la dirección de correo electrónico de los usuarios. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.  <br/> **Última fecha de actividad (UTC)** hace referencia a la última fecha en la que el usuario haya participado en una actividad de Microsoft Teams en una aplicación.  <br/> **Eliminar** indica si se eliminará el equipo. Si el equipo se elimina pero ha tenido actividad en el período del informe, se mostrará en la cuadrícula con esta marca establecida en true.  <br/> **Fecha de eliminación** es la fecha de eliminación del equipo.  <br/> La opción **Windows** aparece seleccionada si el usuario ha estado activo en la aplicación de Windows durante el período de tiempo especificado.  <br/> La opción **Mac** aparece seleccionada si el usuario ha estado activo en una aplicación para Mac durante el período de tiempo especificado.  <br/> La opción **Web** aparece seleccionada si el usuario ha estado activo en una aplicación web durante el período de tiempo especificado.  <br/> La opción **iOS** aparece seleccionada si el usuario ha estado activo en una aplicación de iOS durante el período de tiempo especificado.  <br/> **Teléfono Android** se marca si el usuario ha estado activo en una aplicación para teléfonos Android durante el período de tiempo especificado.  <br/> La opción **Teléfono Windows** aparece seleccionada si el usuario ha estado activo en una aplicación de Windows Phone durante el período de tiempo especificado.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en los [informes de actividades del centro de administración de Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Seleccione **columnas** para agregar o quitar columnas del informe.  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   
  

