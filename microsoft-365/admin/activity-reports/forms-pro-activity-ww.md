---
title: Microsoft 365 Reports en el centro de administración actividad de la voz de clientes de Dynamics 365
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
description: Obtenga información sobre cómo obtener un informe de actividad de voz de cliente de Microsoft Dynamics 365 mediante el panel informes de Microsoft 365 en el centro de administración de Microsoft 365.
ms.openlocfilehash: 0a854c7a89977a96e11d8ec28fd7789e8418c1cf
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988959"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365 Reports en el centro de administración actividad de la voz de clientes de Dynamics 365

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle más información pormenorizada acerca de las actividades dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, puede comprender la actividad de cada usuario con licencia para usar la voz del cliente de Microsoft Dynamics 365 observando sus interacciones con Dynamics 365 Customer Voice. También le ayuda a comprender el nivel de colaboración en el que se ve en el número de encuestas Pro creadas y encuestas profesionales a las que han respondido los usuarios. 
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Cómo obtener el informe de actividad de la voz del cliente de Dynamics 365

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la Página principal del panel, haga clic en el botón **Ver más** de la tarjeta de voz de cliente Dynamics 365.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretar el informe de actividad de la voz del cliente de Dynamics 365

Puede ver las actividades en el informe de voz de cliente Dynamics 365 eligiendo la pestaña **actividad** .<br/>![Microsoft 365 Reports: informe de actividad de la voz del cliente de Microsoft Dynamics 365.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Seleccione **elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de actividad de la voz del cliente de Dynamics 365-elegir columnas](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Elemento|Description|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario que realizó la actividad en Microsoft Forms.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |Última fecha en que el usuario ha realizado una actividad de formulario para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.<br/>Esto filtrará la tabla para mostrar los datos de actividad de archivo solo para los usuarios que realizaron la actividad en ese día específico.  <br/> |
|Número de encuestas creadas  <br/> |El número de encuestas que ha creado el usuario.   <br/> |
|Número de respuestas de la encuesta  <br/> |El número de respuestas de los respondedores a quienes se distribuyó la encuesta.|
|||