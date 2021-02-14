---
title: Usuario activo en informes de uso de Microsoft 365
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Obtenga información sobre un usuario activo de análisis de uso de Microsoft 365, informes de actividades y métricas de adopción.
ms.openlocfilehash: b4834d96b2f762d77f0d27309cf8c71a782b0dcd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402887"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Usuario activo en informes de uso de Microsoft 365

## <a name="active-user-in-usage-reports"></a>Usuario activo en informes de uso

Un usuario activo de los productos de Microsoft 365 [](../activity-reports/activity-reports.md) para el análisis de uso de [Microsoft 365](usage-analytics.md) y los informes de actividad en el centro de administración se define de la siguiente manera. 
  
|**Product**|**Definición de un usuario activo**|**Notas**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Cualquier usuario que lea o envíe un correo electrónico.  <br/> |No se representa información de calendario; esta se agregará en una próxima actualización.  <br/> |
|SharePoint Online  <br/> |Cualquier usuario que interactuó con un archivo al crear, modificar, visualizar, eliminar, compartir (interna o externamente) o sincronizar con clientes en cualquier sitio, o al ver una página en cualquier sitio.  <br/> |La métrica de usuario activo para SharePoint Online en la aplicación de plantilla análisis de uso de Microsoft 365 solo refleja los usuarios que realizaron actividad de archivos en un sitio de grupo o un sitio de grupo de SharePoint. La aplicación de plantilla se actualizará para sincronizar la definición con la misma que en los informes de uso del centro de administración.  <br/> |
|OneDrive para la Empresa  <br/> |Cualquier usuario que interactuó con un archivo al crear, modificar, visualizar, eliminar, compartir (interna o externamente) o sincronizar con clientes.  <br/> ||
|Yammer  <br/> |Cualquier usuario que lea, publique o dé un "me gusta" a un mensaje en Yammer.  <br/> ||
|Skype Empresarial  <br/> |Cualquier usuario que participó en una sesión de punto a punto (como mensajería instantánea, llamadas de vídeo y audio, uso compartido de aplicaciones y transferencias de archivos), o bien que organizó o participó en una conferencia.  <br/> ||
|Office  <br/> |Cualquier usuario que haya activado su suscripción de Microsoft 365 Pro Plus, Visio Pro o Project Pro en al menos un dispositivo.  <br/> ||
|Grupos de Microsoft 365  <br/> |Cualquier miembro de grupo que tenga actividad de buzones (si se envió un mensaje al grupo)  <br/> |Esta definición se mejorará con la actividad de archivo de sitio de grupo y la actividad de grupo de Yammer (actividad de archivo en el sitio de grupo y mensaje publicado en el grupo de Yammer asociado al grupo). Actualmente, estos datos no están disponibles en la aplicación de plantilla análisis de uso de Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Cualquier usuario que haya participado en mensajes de chat, mensajes de chat privados, llamadas, reuniones u otra actividad. Otra actividad se define como el número de otras actividades de equipo por parte del usuario, algunas de las cuales incluyen, entre otras: mensajes de me gusta, aplicaciones, trabajo en archivos, búsqueda, seguimiento de equipos y canales y favoritándolos.  <br/> ||
   
## <a name="adoption-metrics"></a>Métricas de adopción

El análisis de uso de [Microsoft 365](usage-analytics.md) contiene métricas de adopción adicionales relacionadas con los usuarios activos para mostrar la adopción de los productos con el tiempo. Estas métricas son válidas para el mes, el año y el producto seleccionados y se definen de la siguiente manera. 
  
|**Métrica**|**Descripción**|
|:-----|:-----|
|EnabledUsers  <br/> |Número de usuarios habilitados para usar el producto en el mes.  <br/> |
|ActiveUsers  <br/> |Número de usuarios activos en el mes.  <br/> |
|MoMReturningUsers  <br/> |Número de usuarios activos en el mes que también estaban activos en el mes anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuarios activos en el mes que nunca antes habían usado el servicio.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuarios activos en el mes más cualquier mes anterior.  <br/> |
|ActiveUsers(%)  <br/> |Porcentaje de usuarios, redondeado al décimo más cercano, activo en el mes en comparación con el número de usuarios habilitados en ese mes.  <br/> |
|MoMReturningUsers(%)  <br/> |Porcentaje de usuarios, redondeado al décimo más cercano, activo en el mes que también estaba activo en el mes anterior en comparación con el número de usuarios activos.  <br/> |
   
MoMReturningUsers, FirstTimeUsers y CumulativeActiveUsers se restableceron a partir del 1 de enero de &amp; 2018 con la inclusión de Microsoft Teams.
  
