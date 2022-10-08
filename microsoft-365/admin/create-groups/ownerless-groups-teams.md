---
title: Administración de grupos y equipos de Microsoft 365 sin propietario
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
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
description: Obtenga información sobre cómo invitar automáticamente a los miembros a convertirse en propietarios de un grupo de Microsoft 365 sin propietario o de un equipo de Microsoft Teams.
ms.openlocfilehash: b417634638142c749fad12b5e008f2f8d6ff5638
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191351"
---
# <a name="manage-ownerless-microsoft-365-groups-and-teams"></a>Administración de grupos y equipos de Microsoft 365 sin propietario

Un equipo de Microsoft Teams o un grupo de Microsoft 365 y sus servicios relacionados pueden quedar sin propietario si la cuenta de un propietario se elimina o deshabilita en Microsoft 365. Los grupos y equipos requieren que un propietario agregue o quite miembros y cambie la configuración del grupo.

Un administrador global, un administrador de Exchange o un administrador de grupos puede crear una directiva que pregunte automáticamente a los miembros más activos de un grupo o equipo sin propietario si aceptarán la propiedad. Cuando un miembro acepta la invitación para convertirse en propietario, la acción se registra en el registro de auditoría del portal de cumplimiento. Nunca se invita a los huéspedes a ser propietarios.

Al crear la directiva, puede especificar:
- Si desea limitar quién puede ser invitado a ser propietario especificando un grupo de seguridad
- Dirección del remitente de las notificaciones
- El número de semanas que se enviarán las notificaciones
- Qué grupos o equipos forman parte de la directiva

> [!Note]
> El uso de un grupo de seguridad para limitar quién puede ser invitado a ser propietario requiere que posea, pero no necesariamente asigne una licencia premium de Azure AD para cada miembro del grupo de Microsoft 365 de su organización.

Para establecer una directiva de grupo o equipo sin propietario

1. En el Centro de administración, vaya a **Mostrar toda** \> la **configuración Configuración** \> **Configuración De la organización** y, en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">pestaña **Servicios**</a>, seleccione **Grupos de Microsoft 365**.

1. Active la casilla **Cuando no haya propietario, envíe un correo electrónico y pida a los miembros activos del grupo que se conviertan en propietarios** .

1. Si desea mantener los valores de configuración predeterminados, seleccione **Guardar**; de lo contrario, seleccione **Configurar directiva** y complete los pasos siguientes.

1. En la página *Opciones de notificación semanal* , especifique quién puede recibir notificaciones de propiedad. Si decide permitir o bloquear determinados miembros, busque y agregue el grupo de seguridad que desea usar.

1. Escriba el número de miembros activos que desea notificar y seleccione el número de semanas para enviar la notificación. (La lista de notificaciones se crea durante la primera notificación y no cambia). Seleccione **Siguiente**.

1. En la página *Quién es este correo electrónico,* seleccione un remitente para el correo electrónico y, a continuación, seleccione **Siguiente**. Tenga en cuenta que no se admiten buzones compartidos. El remitente debe ser un buzón de usuario o un buzón de grupo.

1. En la página *Asunto y mensaje* , personalice el correo electrónico y, opcionalmente, incluya una **dirección URL de orientación de directiva** y, a continuación, seleccione **Siguiente**.

1. En la página *Seleccionar los grupos de destino* , seleccione **Grupos específicos** y elija los grupos y equipos que desea incluir en esta directiva, o bien seleccione **Todos los grupos**.

1. Seleccione **Siguiente**.

1. En la página *Revisar y finalizar* , confirme la configuración, haga clic en **Finalizar** y, a continuación, seleccione **Listo**.

Las notificaciones se envían semanalmente a partir de las 24 horas posteriores a la creación de la directiva. Los destinatarios no pueden reenviar las notificaciones a otros usuarios. Las notificaciones y respuestas se realizan un seguimiento en el registro de auditoría.

Hasta dos miembros del grupo por grupo pueden aceptar la invitación para convertirse en propietario. Si ningún miembro del grupo acepta, un administrador tendrá que [asignar un propietario de grupo](/admin/create-groups/add-or-remove-members-from-groups).

## <a name="related-topics"></a>Temas relacionados

[Preguntas más frecuentes sobre el grupo sin propietario](/exchange/troubleshoot/groups-and-distribution-lists/ownerless-group-policy)
