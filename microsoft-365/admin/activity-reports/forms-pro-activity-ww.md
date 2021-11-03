---
title: 'Microsoft 365 Informes en el centro de administración: actividad de Dynamics 365 Customer Voice'
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
description: Obtenga información sobre cómo obtener un informe de actividad de Voz del cliente de Microsoft Dynamics 365 mediante el panel Microsoft 365 informes en la Centro de administración de Microsoft 365.
ms.openlocfilehash: d143728f8170ae9c12a6d007e9e256a23f7ff74d
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60650474"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365 Informes en el centro de administración: actividad de Dynamics 365 Customer Voice

El panel Microsoft 365 informes le muestra la introducción a la actividad en todos los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle más información pormenorizada acerca de las actividades dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, puede comprender la actividad de todos los usuarios con licencia para usar Microsoft Dynamics 365 Customer Voice al ver sus interacciones con Dynamics 365 Customer Voice. También le ayuda a comprender el nivel de colaboración que se está creando al ver el número de encuestas de Pro creadas y las encuestas Pro a las que respondieron los usuarios. 
  
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Cómo obtener acceso al informe de actividad de Dynamics 365 Customer Voice

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** de la tarjeta De voz del cliente de Dynamics 365.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretar el informe de actividad de Dynamics 365 Customer Voice

Puede ver las actividades en el informe de Voz del cliente de Dynamics 365 seleccionando la **pestaña** Actividad.<br/>![Microsoft 365: informe de actividad de Microsoft Dynamics 365 Customer Voice.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de actividad de Dynamics 365 Customer Voice: elija columnas.](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 

El informe de actividad de **Dynamics 365 Customer Voice** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará datos hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario que realizó la actividad en Microsoft Forms.  <br/> |
|Fecha de última actividad (UTC)  <br/> |La fecha más reciente en la que el usuario realizó una actividad de formulario para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.<br/>Esto filtrará la tabla para mostrar datos de actividad de archivos solo para los usuarios que realizaron la actividad en ese día específico.  <br/> |
|Número de encuestas creadas  <br/> |Número de encuestas que creó el usuario.   <br/> |
|Número de respuestas a encuestas  <br/> |Número de respuestas de los respondedores a los que se distribuyó la encuesta.|
|||