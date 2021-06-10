---
title: Uso de dispositivo de Microsoft Teams
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Obtenga información sobre las aplicaciones Microsoft Teams que se usan en su organización obteniendo el Microsoft Teams de uso de aplicaciones de Microsoft 365 Informes.
ms.openlocfilehash: 453b5767a6da1361ba8121fa2d49d9db8224aa68
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579631"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365 Informes en el Centro de administración: Microsoft Teams de dispositivos

El panel Microsoft 365 **informes le** muestra la introducción a la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de uso de aplicaciones de Microsoft Teams puede obtener estadísticas sobre las aplicaciones de Microsoft Teams que se usan en su organización.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, servicio de Teams, comunicaciones de Teams o administrador Skype Empresarial para ver informes.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Cómo obtener el informe de uso de aplicaciones de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la **lista desplegable** Seleccionar un informe, seleccione **Microsoft Teams** Uso \> **del dispositivo**.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretar el informe de uso de aplicaciones de Microsoft Teams

Para obtener información sobre el uso de aplicaciones de Microsoft Teams, consulte los gráficos **Usuarios** y **Distribución**. 
  
![Microsoft 365: Microsoft Teams de aplicaciones](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|Elemento|Descripción|
|:-----|:-----|
|1.  <br/> |Puede visualizar el informe **Uso de dispositivos de Microsoft Teams** para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe suelen abarcar hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **Usuarios** muestra el número de usuarios únicos diario por aplicación.  <br/> |
|4.  <br/> |La vista **Distribución** muestra el número de usuarios únicos por aplicación durante el período de tiempo seleccionado.  <br/> |
|5.  <br/> | En el gráfico **Usuarios**, el eje Y es el número de usuarios por aplicación.  <br/>  En el gráfico **Distribución**, el eje Y es el número de usuarios que usa la aplicación especificada.  <br/>  En los dos gráficos, el eje X es el intervalo de fechas seleccionado para el informe específico.  <br/> |
|6.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento en la leyenda. Por ejemplo,  en el gráfico Usuarios, seleccione **Windows**, **Mac**, **Llamadas**, **Web,** **Teléfono Android** o Windows teléfono para ver solo la información relacionada **con** cada uno. Si cambia esta selección, no cambiará la información en la tabla de cuadrícula.  <br/> ![Puedes filtrar los Microsoft Teams de uso de la aplicación seleccionando el tipo de aplicación.](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | La lista de los grupos que se muestra depende de la configuración de todos los grupos que existieron (y que no se eliminaron) a lo largo del plazo para la creación de informes más extenso (180 días). El recuento de actividades variará según la selección de fecha.  <br/> NOTA: Es posible que no vea todos los elementos de la lista siguiente en las columnas hasta que los agregue.<br/> **Nombre de usuario** es la dirección de correo electrónico de los usuarios. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.  <br/> **Última fecha de actividad (UTC)** hace referencia a la última fecha en la que el usuario haya participado en una actividad de Microsoft Teams en una aplicación.  <br/> **Eliminar** indica si se eliminará el equipo. Si el equipo se elimina pero ha tenido actividad en el período del informe, se mostrará en la cuadrícula con esta marca establecida en true.  <br/> **Fecha de eliminación** es la fecha de eliminación del equipo.  <br/> La opción **Windows** aparece seleccionada si el usuario ha estado activo en la aplicación de Windows durante el período de tiempo especificado.  <br/> La opción **Mac** aparece seleccionada si el usuario ha estado activo en una aplicación para Mac durante el período de tiempo especificado.  <br/> La opción **Web** aparece seleccionada si el usuario ha estado activo en una aplicación web durante el período de tiempo especificado.  <br/> La opción **iOS** aparece seleccionada si el usuario ha estado activo en una aplicación de iOS durante el período de tiempo especificado.  <br/> **Teléfono Android** se marca si el usuario ha estado activo en una aplicación para teléfonos Android durante el período de tiempo especificado.  <br/> La opción **Teléfono Windows** aparece seleccionada si el usuario ha estado activo en una aplicación de Windows Phone durante el período de tiempo especificado.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo se ocultan los detalles** del nivel de usuario? en los informes de actividad en [el centro de administración Microsoft 365 usuario.](activity-reports.md)  <br/> |
|8.  <br/> |Seleccione **Columnas** para agregar o quitar columnas del informe.  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |También puede exportar los datos del informe a un Excel .csv, seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   
  

