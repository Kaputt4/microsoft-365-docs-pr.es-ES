---
title: Microsoft 365 directiva de expiración de grupo
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
- m365solution-collabgovernance
search.appverid:
- MET150
recommendations: false
description: Obtenga información sobre las directivas de expiración de grupos de Microsoft 365.
ms.openlocfilehash: 9287d61b95d635eccbbef64d307c0aa0e3d12357
ms.sourcegitcommit: 46e796c6b76a01516c48977335bbf5076ca74a06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "64738565"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 directiva de expiración de grupo

Con el aumento del uso de los grupos de Microsoft 365 y Microsoft Teams, los administradores y los usuarios necesitan una forma de limpiar los grupos y equipos que no usen. Una directiva de expiración de los grupos de Microsoft 365 de expiración puede ayudar a quitar grupos inactivos del sistema y a tener las cosas más limpias.

Cuando un grupo expire, también se eliminarán todos los servicios asociados (el buzón, Planner, el sitio de SharePoint, equipo, etc.).

Cuando un grupo expira, se "elimina temporalmente", lo que significa que todavía se puede recuperar durante un máximo de 30 días.

Los administradores pueden especificar un período de expiración y se eliminará cualquier grupo inactivo que llegue al final de ese período y no se renueve. (Esto incluye equipos archivados). El período de expiración comienza cuando se crea el grupo o en la fecha en que se renovó por última vez. A los propietarios del grupo se les enviará automáticamente un correo electrónico antes de la expiración, lo que les permitirá renovar el grupo para otro intervalo de expiración. Los usuarios de Teams verán notificaciones persistentes en Teams.

Los grupos que se usen activamente se renovarán automáticamente. Cualquiera de las siguientes acciones hará que se renueve automáticamente un grupo:
- SharePoint: ver, editar, descargar, mover, compartir o cargar archivos. (Ver una página de SharePoint no contará como una acción para la renovación automática).
- Outlook: unirse a un grupo o editarlo, leer o escribir un mensaje de grupo del grupo y como un mensaje (Outlook en la Web).
- Teams: visite un canal de teams.
- Yammer: vea una publicación dentro de una comunidad de Yammer o un correo electrónico interactivo en Outlook.
- Formularios: ver, crear o editar formularios, o enviar una respuesta a un formulario. 

Tenga en cuenta que la única actividad Yammer que desencadenará una renovación automática del grupo es la carga de un documento en SharePoint dentro de la comunidad.

> [!IMPORTANT]
> Al cambiar la directiva de expiración, el servicio vuelve a calcular la fecha de expiración de cada grupo. Siempre comienza a contar desde la fecha en que se creó el grupo y, a continuación, aplica la nueva directiva de expiración.

Es importante saber que la expiración está desactivada de forma predeterminada. Los administradores tienen que habilitarlo para su organización si quieren usarlo.

> [!NOTE]
> La configuración y el uso de la directiva de expiración para grupos de Microsoft 365 requiere que posea, pero no necesariamente asigne licencias de Azure AD Premium para los miembros de todos los grupos a los que se aplica la directiva de expiración. Para obtener más información, consulte [Introducción a Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Quién puede configurar y usar la directiva de expiración de grupos de Microsoft 365?

|Rol|Qué pueden hacer|
|---------|---------|
|Office 365 administrador global (en Azure, administrador de empresa), administrador de usuarios|Cree, lea, actualice o elimine la configuración de la directiva de expiración de grupos de Microsoft 365.|
|Usuario|Renovación o [restauración](/azure/active-directory/users-groups-roles/groups-restore-deleted) de un grupo de Microsoft 365 de su propiedad|

## <a name="how-to-set-the-expiration-policy"></a>Cómo establecer la directiva de expiración

Como se indicó anteriormente, la expiración está desactivada de forma predeterminada. Un administrador tendrá que habilitar la directiva de expiración y establecer las propiedades para que surta efecto. Para habilitarlo, vaya a **Azure Active Directory** >  **GroupsExpiration** > . Aquí puede establecer la duración predeterminada del grupo y especificar con qué antelación quiere que las notificaciones de expiración primera y segunda vayan al propietario del grupo.

La duración del grupo se especifica en días y se puede establecer en 180, 365 o en un valor personalizado que especifique. El valor personalizado debe ser de al menos 30 días.

Si el grupo no tiene un propietario, los correos electrónicos de expiración se dirigirán al administrador especificado.

Puede establecer la directiva para todos los grupos, solo los grupos seleccionados (hasta 500) o desactivarla completamente seleccionando **Ninguno**. Tenga en cuenta que actualmente no puede tener directivas diferentes para grupos diferentes.

![Captura de pantalla de la configuración de expiración de grupos en Azure Active Directory.](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Cómo funciona la expiración con la directiva de retención

Si ha configurado una directiva de retención para grupos en el centro de seguridad y cumplimiento, la directiva de expiración funcionará sin problemas con la directiva de retención. Cuando un grupo expire, las conversaciones y los archivos del buzón del grupo en el sitio de grupo se conservarán en el contenedor de retención durante el número específico de días definido en la directiva de retención. Sin embargo, los usuarios no verán el grupo ni su contenido después de que expire.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Cómo y cuándo el propietario de un grupo puede saber si sus grupos van a expirar

Los propietarios del grupo solo recibirán una notificación por correo electrónico. Si el grupo se creó mediante Planner, SharePoint o cualquier otra aplicación, las notificaciones de expiración siempre se enviarán por correo electrónico. Si el grupo se creó mediante Teams, el propietario del grupo recibirá una notificación para renovarlo a través de la sección de actividad. No se recomienda habilitar la expiración en un grupo si el propietario del grupo no tiene una dirección de correo electrónico válida.

30 días antes de que expire el grupo, los propietarios del grupo (o las direcciones de correo electrónico que especificó para los grupos que no tienen propietario) recibirán un correo electrónico que les permitirá renovar fácilmente el grupo. Si no lo renuevan, recibirán otro correo electrónico de renovación 15 días antes de la expiración. Si aún no lo han renovado, recibirán una notificación de correo electrónico más el día antes de la expiración.

Si por alguna razón ninguno de los propietarios o administradores renueva el grupo antes de que expire, el administrador podrá restaurarlo hasta 30 días después de la expiración. Para obtener más información, consulte [Restauración de un grupo de Microsoft 365 eliminado](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Archivado del contenido del grupo

Si tiene un grupo que ya no tiene previsto usar, pero desea conservar su contenido, consulte [Archivar grupos, equipos y Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obtener información sobre cómo exportar información de los distintos servicios de grupos.

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Información general sobre las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configuración de la expiración de grupos de Microsoft 365](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
