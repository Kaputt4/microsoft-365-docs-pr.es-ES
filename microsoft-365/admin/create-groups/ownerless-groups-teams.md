---
title: Administración de grupos y equipos Microsoft 365 sin propietario
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
description: Obtenga información sobre cómo invitar automáticamente a los miembros para que se conviertan en propietarios de un grupo de Microsoft 365 sin propietario o de un equipo de Microsoft Teams.
ms.openlocfilehash: d578e6825ea65177138594034807244afac176c7
ms.sourcegitcommit: 5eff41a350a01e18d9cdd572c9d8ff99d6c9563a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64836462"
---
# <a name="manage-ownerless-microsoft-365-groups-and-teams"></a>Administración de grupos y equipos Microsoft 365 sin propietario

Un equipo de Microsoft Teams o un grupo de Microsoft 365 puede quedar sin propietario si la cuenta de un propietario se elimina o deshabilita en Microsoft 365. Los grupos y equipos requieren que un propietario agregue o quite miembros y cambie la configuración del grupo.

Puede crear una directiva que pregunte automáticamente a los miembros más activos o a un grupo o equipo sin propietario si aceptan la propiedad. Cuando un miembro acepta la invitación para convertirse en propietario, la acción se registra en el registro de auditoría del Centro de cumplimiento. Nunca se invita a los huéspedes a ser propietarios.

Al crear la directiva, puede especificar:
- Si desea limitar quién puede ser invitado a ser propietario especificando un grupo de seguridad
- Dirección del remitente de las notificaciones
- El número de semanas que se enviarán las notificaciones
- Qué grupos o equipos forman parte de la directiva

Para establecer una directiva de grupo o equipo sin propietario

1. En el centro de administración, vaya a **Mostrar todos los** \> **Configuración** \> **configuración de la organización** y, en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">pestaña **Servicios**</a>, seleccione **Grupos de Microsoft 365**.

1. Active la casilla **Cuando no haya propietario, envíe un correo electrónico y pida a los miembros activos del grupo que se conviertan en propietarios** .

1. Si desea mantener los valores de configuración predeterminados, seleccione **Guardar**; de lo contrario, seleccione **Configurar directiva** y complete los pasos siguientes.

1. En la página *Opciones de notificación semanal* , especifique quién puede recibir notificaciones de propiedad. Si decide permitir o bloquear determinados miembros, busque y agregue el grupo de seguridad que desea usar.

1. Escriba el número de miembros activos que desea notificar y seleccione el número de semanas para enviar la notificación. (La lista de notificaciones se crea durante la primera notificación y no cambia). Seleccione **Siguiente**.

1. En la *Quién este correo electrónico procede de la* página, seleccione un remitente para el correo electrónico y, a continuación, seleccione **Siguiente**.

1. En la página *Asunto y mensaje* , personalice el correo electrónico y, opcionalmente, incluya una **dirección URL de orientación de directiva** y, a continuación, seleccione **Siguiente**.

1. En la página *Seleccionar los grupos de destino* , seleccione **Grupos específicos** y elija los grupos y equipos que desea incluir en esta directiva, o bien seleccione **Todos los grupos**.

1. Seleccione **Siguiente**.

1. En la página *Revisar y finalizar* , confirme la configuración, haga clic en **Finalizar** y, a continuación, seleccione **Listo**.

Las notificaciones se envían semanalmente a partir de las 24 horas posteriores a la creación de la directiva.