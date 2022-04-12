---
title: Centro de administración de Microsoft 365 Yammer informes de uso del dispositivo
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
description: Obtenga el informe de uso del dispositivo Yammer para saber en qué dispositivos usan Yammer los usuarios.
ms.openlocfilehash: 265cef494349daba8b7e526ad6b7c6abd61adcf7
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781281"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>informes de Microsoft 365 en el centro de administración: Yammer informe de uso del dispositivo

En el panel informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Los informes de uso de dispositivos de Yammer proporcionan información sobre los dispositivos en los que los usuarios utilizan Yammer. Puede ver el número de usuarios, tanto diarios como en general, por tipo de dispositivo. Además, puede consultar ambos valores un período de tiempo determinado. Asimismo, también puede ver los detalles de cada usuario.
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>¿Cómo puedo tener acceso al informe de uso de dispositivos de Yammer?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la tarjeta Yammer.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretación del informe de uso del dispositivo Yammer

Para ver el uso en el informe de OneDrive, elija la pestaña **Uso del dispositivo**.<br/>![informes de Microsoft 365: informe de uso de dispositivos de Microsoft Yammer.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Yammer informe de uso del dispositivo: elija columnas.](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el vínculo **Exportar**. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 

El **informe de uso de Yammer dispositivo** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. En esta cuadrícula se muestran los usuarios que han iniciado sesión en Yammer con la cuenta de Microsoft 365 o que han iniciado sesión en la red mediante el inicio de sesión único. <br/> |
|Nombre para mostrar  <br/> |Nombre completo del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.  <br/> |
|Estado del usuario  <br/> |Uno de los tres valores: Activo, Eliminado o Suspendido. En estos informes se muestran datos para usuarios activos, suspendidos y eliminados. No reflejan usuarios pendientes, porque los usuarios pendientes no publican, leen o indican que les gusta un mensaje.   <br/> |
|Fecha de cambio de estado (UTC)  <br/> |Fecha en la que se cambió el estado del usuario en Yammer.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La última fecha (UTC) en la que el usuario participó en una actividad de Yammer.  <br/> |
|Web  <br/> |Indica si el usuario ha usado Yammer en la web.  <br/> |
|teléfono Windows  <br/> | Indica si el usuario ha usado Yammer en un teléfono Windows.  <br/> |
|Teléfono Android  <br/> |Indica si el usuario ha usado Yammer en un teléfono Android. <br/>|
|Iphone <br/> | Indica si el usuario ha usado Yammer en un iPhone.  <br/> |
|Ipad  <br/> |Indica si el usuario ha usado Yammer en un iPad. <br/>|
|Otro  <br/> |Indica si el usuario ha usado Yammer en otro dispositivo, no enumerado anteriormente. <br/>|
|||