---
title: Usuario activo en informes de uso de Microsoft 365
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Obtenga información sobre un usuario activo de análisis de uso de Microsoft 365, informes de actividad y métricas de adopción.
ms.openlocfilehash: bddd946c9062d7fa98c5c88091ef8d92f4372e4e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193463"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Usuario activo en informes de uso de Microsoft 365

## <a name="active-user-in-usage-reports"></a>Usuario activo en informes de uso

Un usuario activo de los productos de Microsoft 365 para el [análisis de uso de Microsoft 365](usage-analytics.md) y los [informes de actividad en el Centro de administración](../activity-reports/activity-reports.md) se definen de la siguiente manera. 
  
|**Producto**|**Definición de un usuario activo**|**Notas**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Cualquier usuario que haya realizado cualquiera de las siguientes acciones: Marcar como leído, enviar mensajes, crear citas, enviar convocatorias de reunión, aceptar (como provisional) o rechazar convocatorias de reunión, cancelar reuniones.  <br/> |No se representa información de calendario; esta se agregará en una próxima actualización.  <br/> |
|SharePoint Online  <br/> |Cualquier usuario que interactuó con un archivo al crear, modificar, visualizar, eliminar, compartir (interna o externamente) o sincronizar con clientes en cualquier sitio, o al ver una página en cualquier sitio.  <br/> |Las métricas de usuario activas para SharePoint Online en la aplicación de plantilla Análisis de uso de Microsoft 365 solo reflejan los usuarios que realizaron actividad de archivo en un sitio de grupo o un sitio de grupo de SharePoint. La aplicación de plantilla se actualizará para sincronizar la definición con la misma que en los informes de uso del Centro de administración.  <br/> |
|OneDrive para la Empresa  <br/> |Cualquier usuario que interactuó con un archivo al crear, modificar, visualizar, eliminar, compartir (interna o externamente) o sincronizar con clientes.  <br/> ||
|Yammer  <br/> |Cualquier usuario que lea, publique o dé un "me gusta" a un mensaje en Yammer.  <br/> ||
|Skype Empresarial  <br/> |Cualquier usuario que participó en una sesión de punto a punto (como mensajería instantánea, llamadas de vídeo y audio, uso compartido de aplicaciones y transferencias de archivos), o bien que organizó o participó en una conferencia.  <br/> ||
|Oficina  <br/> |Cualquier usuario que haya activado su suscripción a Microsoft 365 Pro Plus, Visio Pro o Project Pro en al menos un dispositivo.  <br/> ||
|Grupos de Microsoft 365  <br/> |Cualquier miembro de grupo que tenga actividad de buzones (si se envió un mensaje al grupo)  <br/> |Esta definición se mejorará con la actividad de archivo de sitio de grupo y la actividad de grupo de Yammer (actividad de archivo en el sitio del grupo y mensaje publicado en el grupo de Yammer asociado al grupo). Estos datos no están disponibles actualmente en la aplicación de plantilla Análisis de uso de Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Cualquier usuario que haya participado en mensajes de chat, mensajes de chat privados, llamadas, reuniones u otra actividad. Otra actividad se define como el número de otras actividades de equipo por parte del usuario algunas de las cuales incluyen, y no se limitan a: me gustar mensajes, aplicaciones, trabajar en archivos, buscar, seguir equipos y canalizar y favorecerlos.  <br/> ||
   
## <a name="adoption-metrics"></a>Métricas de adopción

[El análisis de uso de Microsoft 365](usage-analytics.md) contiene más métricas de adopción relacionadas con los usuarios activos para mostrar la adopción de los productos a lo largo del tiempo. Estas métricas son válidas para el mes, el año y el producto seleccionado y se definen de la siguiente manera. 
  
|**Métrica**|**Descripción**|
|:-----|:-----|
|EnabledUsers  <br/> |Número de usuarios habilitados para usar el producto en el mes.  <br/> |
|ActiveUsers  <br/> |Número de usuarios activos en el mes.  <br/> |
|MoMReturningUsers  <br/> |Número de usuarios activos en el mes que también estaban activos en el mes anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuarios activos en el mes que nunca antes habían usado el servicio.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuarios activos en el mes más cualquier mes anterior.  <br/> |
|ActiveUsers(%)  <br/> |Porcentaje de usuarios, redondeados a la décima más cercana, activos en el mes en comparación con el número de usuarios habilitados en ese mes.  <br/> |
|MoMReturningUsers(%)  <br/> |Porcentaje de usuarios, redondeados a la décima más cercana, activos en el mes que también estaban activos en el mes anterior en comparación con el número de usuarios activos.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers se restableceron a partir del 1 de enero de 2018 con la inclusión de Microsoft Teams.
  
