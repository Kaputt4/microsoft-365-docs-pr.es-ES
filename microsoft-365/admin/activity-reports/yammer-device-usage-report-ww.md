---
title: Centro de administración de Microsoft 365 informes de uso de dispositivos de Yammer
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el informe de uso de dispositivos de Yammer para obtener más información sobre los dispositivos en los que los usuarios usan Yammer, el número de usuarios diarios por tipo de dispositivo y los detalles por usuario.
ms.openlocfilehash: 5be41a946f110c809cc45a8fa9b0cdb21c0a9f35
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722494"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Informes de Microsoft 365 en el Centro de administración: informe de uso de dispositivos yammer

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte el [tema Información general sobre informes](activity-reports.md).
  
The Yammer device usage reports give you information about which devices your users are using Yammer on. You can view the number of daily users by device type, and number of users by device type. You can view both over a selected time period. You can also view details per user.
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>¿Cómo puedo tener acceso al informe de uso de dispositivos de Yammer?

1. En el centro de administración, vaya a **Informes** y, a continuación, seleccione **Uso**. 
2. En la página principal del panel, seleccione **Ver más** en la tarjeta de Yammer.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretación del informe de uso del dispositivo Yammer

Seleccione la pestaña **Uso del dispositivo** para ver el uso en el informe de OneDrive.

:::image type="content" source="../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png" alt-text="Informes de Microsoft 365: informe de uso del dispositivo Yammer de Microsoft.":::

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  

:::image type="content" source="../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png" alt-text="Informe de uso de dispositivos de Yammer: elija columnas.":::

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo Exportar. Este vínculo exporta datos de todos los usuarios y le permite realizar una ordenación y un filtrado sencillos para un análisis posterior.

El informe **de uso de dispositivos de Yammer** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Métrica|Definición|
|:-----|:-----|
|Nombre de usuario  |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. En esta cuadrícula se muestran los usuarios que han iniciado sesión en Yammer con la cuenta de Microsoft 365 o que han iniciado sesión en la red mediante el inicio de sesión único.  |
|Nombre para mostrar |Nombre completo del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. |
|Estado del usuario |Uno de los tres valores: Activo, Eliminado o Suspendido. En estos informes se muestran datos para usuarios activos, suspendidos y eliminados. No reflejan los usuarios pendientes, porque los usuarios pendientes no pueden publicar, leer o como un mensaje.   |
|Fecha de cambio de estado (UTC)  |Fecha en la que se cambió el estado del usuario en Yammer.  |
|Fecha de la última actividad (UTC) |La última fecha (UTC) en la que el usuario participó en una actividad de Yammer. |
|Web  |Indica si el usuario ha usado Yammer en la web.   |
|Windows Phone   | Indica si el usuario ha usado Yammer en un teléfono Windows.  |
|Teléfono Android  |Indica si el usuario ha usado Yammer en un teléfono Android. |
|iPhone  | Indica si el usuario ha usado Yammer en un iPhone.  |
|iPad   |Indica si el usuario ha usado Yammer en un iPad. |
|Otro  |Indica si el usuario ha usado Yammer en otro cliente, que no se ha enumerado anteriormente. Esto incluye Yammer Embed, SharePoint Web Part, Viva Engage y seleccione Correos electrónicos de Outlook.  |
