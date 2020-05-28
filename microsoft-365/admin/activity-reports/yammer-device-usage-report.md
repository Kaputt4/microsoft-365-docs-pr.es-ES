---
title: 'Informes de Microsoft 365 en el centro de administración: informe de uso de dispositivos de Yammer'
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b793ffdd-effa-43d0-849a-b1ca2e899f38
description: 'Obtenga el informe de uso de dispositivos de Yammer para conocer los dispositivos en los que los usuarios usan Yammer. '
ms.openlocfilehash: 17fcf6c7d46988f0783b5097d3381b9bc08cbbe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387458"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Informes de Microsoft 365 en el centro de administración: informe de uso de dispositivos de Yammer

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Los informes de uso de dispositivos de Yammer proporcionan información sobre los dispositivos en los que los usuarios utilizan Yammer. Puede ver el número de usuarios, tanto diarios como en general, por tipo de dispositivo. Además, puede consultar ambos valores un período de tiempo determinado. Asimismo, también puede ver los detalles de cada usuario.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes. 
  
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>¿Cómo puedo tener acceso al informe de uso de dispositivos de Yammer?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione **Yammer** \> **uso de dispositivos**de Yammer.
  
## <a name="interpret-the-yammer-activity-report"></a>Interpretar el informe de actividad de Yammer

Para obtener información sobre el uso de dispositivos de Yammer de sus usuarios, consulte los gráficos **Usuarios** y **Distribución**. 
  
El informe de uso de dispositivos contiene la siguiente información.
  
- Use las pestañas de día para ver las tendencias del informe de actividad de **uso de dispositivos de Yammer** en los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe). 
    
- Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad.
    
- Para ver el número de usuarios diarios por tipo de dispositivo, consulte el gráfico **Usuarios**.<br/>![Vista de usuarios en el gráfico de uso de dispositivos de Yammer](../../media/ecfba1ec-fbea-4491-88da-1fb19b4d5629.png)<br/>![Informe de uso de dispositivos de Yammer que muestra la vista de usuarios](../../media/f396865a-ad6e-4f8b-a145-cc3865b352f4.png)
  
- Para ver el número de usuarios por tipo de dispositivo, consulte el gráfico **Distribución**.<br/>![Vista de distribución en el informe de uso de dispositivos de Yammer](../../media/7a0b152e-2d2b-4d23-8dc2-046be53b724f.png)<br/>![Informe de uso de dispositivos de Yammer](../../media/780c351d-7a1d-451d-8c16-4c454ef58aa8.png)
  
- En la tabla **Detalles** que encontrará debajo del gráfico, se muestra un desglose del uso de dispositivos de Yammer en el nivel de usuario. 
    
    También puede agregar y quitar columnas. Las columnas disponibles son:
    
  - **Nombre de usuario** es la dirección de correo electrónico de los usuarios. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. 
    
    Esta cuadrícula muestra a los usuarios que iniciaron sesión en Yammer con la cuenta de Microsoft 365 o que iniciaron sesión en la red con el inicio de sesión único.
    
  - **Nombre para mostrar** corresponde al nombre completo del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. 
    
  - **Estado del usuario** corresponde a uno de estos tres valores: Activo, Eliminado o Suspendido. 
    
    En estos informes se muestran datos para usuarios activos, suspendidos y eliminados. No reflejan usuarios pendientes, porque los usuarios pendientes no publican, leen o indican que les gusta un mensaje.
    
  - **Web** indica si el usuario ha utilizado Yammer en la Web. 
    
  - **Teléfono Windows** indica si el usuario ha utilizado Yammer en un teléfono Windows. 
    
  - **Teléfono Android** indica si el usuario ha utilizado Yammer en un teléfono Android. 
    
  - **iPhone** indica si el usuario ha utilizado Yammer en un iPhone. 
    
  - **iPad** indica si el usuario ha utilizado Yammer en un iPad. 
    
  - **Otro** indica si el usuario ha utilizado Yammer en otro dispositivo no mencionado anteriormente. 
    
    Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en los [informes de actividades del centro de administración de Microsoft 365](activity-reports.md).
    
- También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
    

