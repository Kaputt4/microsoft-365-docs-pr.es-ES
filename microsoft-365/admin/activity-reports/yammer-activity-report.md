---
title: 'Informes de Microsoft 365 en el centro de administración: informe de actividad de Yammer'
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a
description: Obtenga el informe de actividad de Yammer y sepa más sobre el número de usuarios que usan Yammer para publicar, como, o leer un mensaje.
ms.openlocfilehash: 2bf02c0599f999b0eebb52d119096567bb09508b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387470"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Informes de Microsoft 365 en el centro de administración: informe de actividad de Yammer

Como administrador de Microsoft 365, el panel **informes** muestra los datos de uso de los productos de la organización. Consulte [los informes de actividad en el centro de administración](activity-reports.md). Con el **informe de actividad de Yammer**, podrá comprender el nivel de participación de la organización con Yammer consultando el número de usuarios únicos que usan Yammer para publicar, leer o indicar que les gusta un mensaje, y la cantidad de actividad generada en toda la organización. 
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes. 
 
## <a name="how-to-get-to-the-yammer-activity-report"></a>Obtener acceso al informe de actividad de Yammer

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione **Yammer** \> **actividad**de Yammer.
  
## <a name="interpret-the-yammer-activity-report"></a>Interpretar el informe de actividad de Yammer

Puede obtener una vista de la actividad de Yammer del usuario consultando los gráficos Actividad y Usuarios.
  
![Informe de actividad de Yammer](../../media/92e8b2c6-166a-4154-9824-3fb6bbedf0db.JPG)
  
El informe de actividad contiene la siguiente información.
  
- Use las pestañas de los días para ver las tendencias del informe de **actividades de Yammer** de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe). 
    
- Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad.
    
- Puede ver el gráfico **Actividad** para comprender la tendencia de la cantidad de actividad de Yammer en su organización. Podrá comprender la división de mensajes publicados, leídos o que han gustado. 
    
    ![Vista de actividad en el informe de actividad de Yammer](../../media/76983516-2c5f-43a1-a5e3-c414e9f17638.JPG)
  
  - En el gráfico **Actividad**, el eje Y es el recuento de las actividades de los mensajes que se han publicado, leído o que han gustado. 
    
- Puede ver el gráfico **Usuario** para comprender la tendencia de la cantidad de usuarios únicos que generan las actividades de Yammer. Puede consultar la tendencia de los usuarios que publican, leen o a quienes les gustan mensajes de Yammer. 
    
    ![Usuarios ven en el informe de actividad de Yammer](../../media/b1098162-7b79-430f-bfe4-9d3957d56885.JPG)
  
  - En el gráfico de actividad **Usuarios**, el eje Y es el usuario que publica, lee o le gustan mensajes de Yammer. 
    
  - En ambos gráficos, el eje X es el intervalo de fechas seleccionado para este informe específico.
    
- Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **actividad** , seleccione **publicado**, **leído**o **me gusta** ver solo la información relacionada con cada uno de ellos. 
    
    ![Opciones de publicación, lectura y gusta](../../media/8b832afc-415c-409b-816f-cb02b7a71e69.png)
  
    Al cambiar esta selección, no se cambia la información de la tabla de cuadrícula.
    
- En la tabla del gráfico se muestra un desglose de las actividades de Yammer en el nivel de usuario.
    
    Puede usar el menú para filtrar y ordenar los datos.
    
    ![Opciones de menú para informes de Yammer](../../media/9d32240c-f1ff-400b-9c4e-a21b48651530.JPG)
  
    También puede agregar y quitar columnas. Las columnas disponibles son:
    
  - **Nombre de usuario** es la dirección de correo electrónico de los usuarios. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. 
    
    Esta cuadrícula muestra a los usuarios que iniciaron sesión en Yammer con la cuenta de Microsoft 365 o que iniciaron sesión en la red con el inicio de sesión único.
    
  - **Nombre para mostrar** es el nombre completo del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo. 
    
  - **Estado del usuario** es uno de estos tres valores: Activado, Eliminado o Suspendido. 
    
    En estos informes se muestran datos para usuarios activos, suspendidos y eliminados. No reflejan usuarios pendientes, porque los usuarios pendientes no publican, leen o indican que les gusta un mensaje.
    
  - **Fecha de cambio de estado (UTC)** es la fecha en la que se cambió el estado del usuario en Yammer. 
    
  - **Última fecha de actividad (UTC)** hace referencia a la última fecha en la que el usuario publicó, leyó o indicó que le gustaba un mensaje. 
    
  - **Publicado** es el número de mensajes que el usuario publicó durante el período de tiempo especificado. 
    
  - **Leído** es el número de conversaciones que el usuario leyó durante el período de tiempo especificado. 
    
  - **Me gusta** es el número de mensajes que le gustaron al usuario durante el período de tiempo especificado. 
    
  - **Producto asignado** son los productos que se asignan a este usuario. 
    
    Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en [informes de actividad en el centro de administración de Microsoft 365](activity-reports.md).
    
- También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
    
## <a name="what-data-is-in-these-reports"></a>¿Qué datos se incluyen en estos informes?

- **Todos los clientes** Estos informes agregan datos entre todos los clientes, incluido el uso de Yammer en un explorador o en una aplicación para Android o iOS. 
    
- **No hay datos de la red externa** Los datos de la red externa no se incluyen en estos informes. 
    
- **Redes activadas** Estos informes muestran los datos de la red de Yammer que forma parte de la suscripción a Microsoft 365. El gráfico agrega el uso de todos los usuarios que iniciaron sesión en la red de Yammer, independientemente de si usaban Microsoft 365 o Yammer para iniciar sesión. 
    

