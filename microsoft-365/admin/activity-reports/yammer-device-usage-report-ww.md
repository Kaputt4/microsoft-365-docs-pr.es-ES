---
title: 'Informes de Microsoft 365 en el centro de administración: informe de uso de dispositivos de Yammer'
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
description: Obtenga el informe de uso de dispositivos de Yammer para conocer los dispositivos en los que los usuarios usan Yammer.
ms.openlocfilehash: fae76e9ef769248217140c059004efc7ad330928
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779416"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Informes de Microsoft 365 en el centro de administración: informe de uso de dispositivos de Yammer

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Los informes de uso de dispositivos de Yammer proporcionan información sobre los dispositivos en los que los usuarios utilizan Yammer. Puede ver el número de usuarios, tanto diarios como en general, por tipo de dispositivo. Además, puede consultar ambos valores un período de tiempo determinado. Asimismo, también puede ver los detalles de cada usuario.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>¿Cómo puedo tener acceso al informe de uso de dispositivos de Yammer?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la Página principal del panel, haga clic en el botón **Ver más** de la tarjeta de Yammer.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretar el informe de uso de dispositivos de Yammer

Puede ver el uso en el informe de OneDrive eligiendo la pestaña **uso de dispositivo** .<br/>![Microsoft 365 Reports-informe de uso de dispositivos de Microsoft Yammer.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Seleccione **elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de uso de dispositivos de Yammer: elegir columnas](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. Esta cuadrícula muestra a los usuarios que iniciaron sesión en Yammer con la cuenta de Microsoft 365 o que iniciaron sesión en la red con el inicio de sesión único. <br/> |
|Nombre para mostrar  <br/> |El nombre completo del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.  <br/> |
|Estado del usuario  <br/> |Uno de estos tres valores: activo, eliminado o suspendido. En estos informes se muestran datos para usuarios activos, suspendidos y eliminados. No reflejan usuarios pendientes, porque los usuarios pendientes no publican, leen o indican que les gusta un mensaje.   <br/> |
|Fecha de cambio de estado (UTC)  <br/> |La fecha en la que se modificó el estado del usuario en Yammer.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La última fecha (UTC) en la que el usuario participó en una actividad de Yammer.  <br/> |
|Web  <br/> |Indica si el usuario ha utilizado Yammer en la Web.  <br/> |
|Windows Phone  <br/> | Indica si el usuario ha utilizado Yammer en un Windows Phone.  <br/> |
|Teléfono Android  <br/> |Indica si el usuario ha utilizado Yammer en un teléfono Android. <br/>|
|dispositivo <br/> | Indica si el usuario ha utilizado Yammer en un iPhone.  <br/> |
|dispositivos  <br/> |Indica si el usuario ha utilizado Yammer en un iPad. <br/>|
|otro  <br/> |Indica si el usuario ha utilizado Yammer en otro dispositivo, pero no se ha mostrado anteriormente. <br/>|
|||