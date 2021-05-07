---
title: 'Microsoft 365 Informes en el Centro de administración: informe Yammer de uso de dispositivos'
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
description: Obtén el Yammer de uso del dispositivo para saber qué dispositivos usan los usuarios Yammer dispositivos.
ms.openlocfilehash: 817627cac791d35f49cd240ceb48de15ef328ef8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241849"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365 Informes en el Centro de administración: informe Yammer de uso de dispositivos

El panel Microsoft 365 **informes le** muestra la introducción a la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Los informes de uso de dispositivos de Yammer proporcionan información sobre los dispositivos en los que los usuarios utilizan Yammer. Puede ver el número de usuarios, tanto diarios como en general, por tipo de dispositivo. Además, puede consultar ambos valores un período de tiempo determinado. Asimismo, también puede ver los detalles de cada usuario.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, servicio de Teams, comunicaciones de Teams o administrador Skype Empresarial para ver informes.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>¿Cómo puedo tener acceso al informe de uso de dispositivos de Yammer?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el **botón Ver más** en la Yammer panel.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretar el informe Yammer uso de dispositivos

Puedes ver el uso en el informe de OneDrive seleccionando la **pestaña Uso del** dispositivo.<br/>![Microsoft 365: informe de uso Yammer dispositivo de Microsoft.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Yammer de uso de dispositivos: elija columnas](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. Esta cuadrícula muestra a los usuarios que iniciaron sesión Yammer la cuenta Microsoft 365 o que iniciaron sesión en la red mediante el inicio de sesión único. <br/> |
|Nombre para mostrar  <br/> |Nombre completo del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.  <br/> |
|Estado del usuario  <br/> |Uno de tres valores: Activo, Eliminado o Suspendido. En estos informes se muestran datos para usuarios activos, suspendidos y eliminados. No reflejan usuarios pendientes, porque los usuarios pendientes no publican, leen o indican que les gusta un mensaje.   <br/> |
|Fecha de cambio de estado (UTC)  <br/> |La fecha en la que se cambió el estado del usuario en Yammer.  <br/> |
|Fecha de última actividad (UTC)  <br/> |La última fecha (UTC) en la que el usuario participó en una Yammer actividad.  <br/> |
|Web  <br/> |Indica si el usuario ha usado Yammer en la web.  <br/> |
|Windows teléfono  <br/> | Indica si el usuario ha usado Yammer en un Windows teléfono.  <br/> |
|Teléfono Android  <br/> |Indica si el usuario ha usado Yammer en un teléfono Android. <br/>|
|iphone <br/> | Indica si el usuario ha usado Yammer en un iPhone.  <br/> |
|ipad  <br/> |Indica si el usuario ha usado Yammer en un iPad. <br/>|
|otros  <br/> |Indica si el usuario ha usado Yammer en otro dispositivo, no enumerado anteriormente. <br/>|
|||