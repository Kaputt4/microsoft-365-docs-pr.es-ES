---
title: Usuario activo en los informes de uso de Microsoft 365
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Obtenga información sobre un usuario activo de los análisis de uso de Microsoft 365, informes de actividades y métricas de adopción.
ms.openlocfilehash: 2117bae32913ad713318c1df25be66d6ef6859e5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631796"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Usuario activo en los informes de uso de Microsoft 365

## <a name="active-user-in-usage-reports"></a>Usuario activo en informes de uso

Un usuario activo de productos de Microsoft 365 para [microsoft 365 Usage Analytics](usage-analytics.md) y los [informes de actividades en el centro de administración](../activity-reports/activity-reports.md) se definen de la siguiente manera. 
  
|**Product**|**Definición de un usuario activo**|**Notas**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Cualquier usuario que lea o envíe un correo electrónico.  <br/> |No se representa información de calendario; esta se agregará en una próxima actualización.  <br/> |
|SharePoint Online  <br/> |Cualquier usuario que interactuó con un archivo al crear, modificar, visualizar, eliminar, compartir (interna o externamente) o sincronizar con clientes en cualquier sitio, o al ver una página en cualquier sitio.  <br/> |La métrica de usuarios activos de SharePoint Online en la aplicación de plantilla de análisis de uso de Microsoft 365 sólo refleja a los usuarios que realizaron actividades de archivos en un sitio de grupo de SharePoint o un sitio de grupo. La aplicación de plantilla se actualizará para sincronizar la definición con el mismo que en los informes de uso del centro de administración.  <br/> |
|OneDrive para la Empresa  <br/> |Cualquier usuario que interactuó con un archivo al crear, modificar, visualizar, eliminar, compartir (interna o externamente) o sincronizar con clientes.  <br/> ||
|Yammer  <br/> |Cualquier usuario que lea, publique o dé un "me gusta" a un mensaje en Yammer.  <br/> ||
|Skype Empresarial  <br/> |Cualquier usuario que participó en una sesión de punto a punto (como mensajería instantánea, llamadas de vídeo y audio, uso compartido de aplicaciones y transferencias de archivos), o bien que organizó o participó en una conferencia.  <br/> ||
|Office  <br/> |Cualquier usuario que haya activado su suscripción a Microsoft 365 Pro Plus, Visio Pro o Project Pro en al menos un dispositivo.  <br/> ||
|Grupos de 365 de Microsoft  <br/> |Cualquier miembro de grupo que tenga actividad de buzones (si se envió un mensaje al grupo)  <br/> |Esta definición se mejorará con la actividad de archivo del sitio de grupo y la actividad de grupo de Yammer (actividad de archivos en el sitio de grupo y mensaje expuesto en el grupo de Yammer asociado con el grupo). Actualmente, estos datos no están disponibles en la aplicación de plantilla de análisis de uso de Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Cualquier usuario que haya participado en mensajes de chat, mensajes privados de chat, llamadas, reuniones u otra actividad. Otra actividad se define como el número de otras actividades del equipo por parte del usuario, algunas de las cuales incluyen y no se limitan a los mensajes de gustos, las aplicaciones, el trabajo en archivos, la búsqueda, los siguientes equipos y el canal y favoriting.  <br/> ||
   
## <a name="adoption-metrics"></a>Métricas de adopción

El [análisis de uso de Microsoft 365](usage-analytics.md) contiene métricas de adopción adicionales relacionadas con los usuarios activos para mostrar la adopción de los productos a lo largo del tiempo. Estas métricas son válidas para el mes, año y producto seleccionados y se definen de la siguiente manera. 
  
|**Biometría**|**Descripción**|
|:-----|:-----|
|EnabledUsers  <br/> |Número de usuarios habilitados para usar el producto en el mes.  <br/> |
|ActiveUsers  <br/> |Número de usuarios activos en el mes.  <br/> |
|MoMReturningUsers  <br/> |Número de usuarios activos en el mes que también estaban activos en el mes anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuarios activos en el mes que nunca han usado el servicio anteriormente.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuarios activos en el mes más el mes anterior.  <br/> |
|ActiveUsers (%)  <br/> |Porcentaje de usuarios, redondeado a la décima más cercana, activo en el mes comparado con el número de usuarios habilitados en ese mes.  <br/> |
|MoMReturningUsers (%)  <br/> |Porcentaje de usuarios, redondeados a la décima más cercana, activos en el mes que también estaban activos en el mes anterior y comparados con el número de usuarios activos.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers se restablecieron a partir del 1 de enero de 2018 con la inclusión de Microsoft Teams.
  
