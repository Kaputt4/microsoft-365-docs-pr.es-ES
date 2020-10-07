---
title: Directiva de expiración de grupo 365 de Microsoft
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Obtenga información sobre las directivas de expiración de grupos de 365 de Microsoft.
ms.openlocfilehash: 8fc9c48d5a86c68eabd4139ad0a2d0dc1e83da0f
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377228"
---
# <a name="microsoft-365-group-expiration-policy"></a>Directiva de expiración de grupo 365 de Microsoft

Con el aumento en el uso de los grupos de Microsoft 365 y Microsoft Teams, los administradores y los usuarios necesitan una forma de limpiar los grupos y equipos que no se usan. Una directiva de expiración de grupos de 365 de Microsoft puede ayudar a quitar los grupos inactivos del sistema y a hacer que los elementos sean más limpios.

Cuando un grupo expira, también se eliminan todos los servicios asociados (buzón de correo, programador, sitio de SharePoint, equipo, etc.).

Cuando un grupo expira, se "elimina temporalmente", lo que significa que todavía se puede recuperar hasta 30 días.

Los administradores pueden especificar un período de expiración y los grupos inactivos que alcanzan el final de dicho período, y no se renuevan, se eliminarán. (Esto incluye a los equipos archivados). El período de expiración comienza cuando se crea el grupo o en la fecha en que se renovó por última vez. A los propietarios de grupos se les enviará automáticamente un correo electrónico antes de la expiración que les permite renovar el grupo para otro intervalo de expiración. Los usuarios de Microsoft Teams verán las notificaciones persistentes en Teams.

Los grupos que se están usando activamente se renuevan automáticamente. Cualquiera de las acciones siguientes renovará automáticamente un grupo:
- SharePoint: ver, editar, descargar, mover, compartir o cargar archivos.
- Outlook: unirse a un grupo, leer o escribir un mensaje de grupo del grupo y como un mensaje (Outlook en la web).
- Microsoft Teams: visitar un canal de Teams.

> [!IMPORTANT]
> Al cambiar la Directiva de expiración, el servicio vuelve a calcular la fecha de caducidad para cada grupo. Siempre comienza a contar desde la fecha en que se creó el grupo y, a continuación, aplica la nueva Directiva de expiración.

Es importante saber que la expiración está desactivada de forma predeterminada. Los administradores deben habilitarla para su organización si desean usarla.

> [!NOTE]
> La configuración y el uso de la Directiva de expiración de los grupos de Microsoft 365 requieren la posesión de licencias de Azure AD Premium, pero no necesariamente asignarlas a los miembros de todos los grupos a los que se aplique la Directiva de expiración. Para obtener más información, consulte [Getting Started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>¿Quién puede configurar y usar la Directiva de expiración de grupos de 365 de Microsoft?

|Función|Qué pueden hacer|
|---------|---------|
|Office 365 administrador global (en Azure, el administrador de la compañía), administrador del usuario|Cree, lea, actualice o elimine la configuración de la Directiva de expiración de grupos de 365 de Microsoft.|
|Usuario|Renovar o [restaurar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) un grupo de Microsoft 365 que son de su propiedad|

## <a name="how-to-set-the-expiration-policy"></a>Cómo establecer la Directiva de expiración

Como se indicó anteriormente, la expiración está desactivada de forma predeterminada. Un administrador tendrá que habilitar la Directiva de expiración y establecer las propiedades para que surta efecto. Para habilitarla, vaya **Azure Active Directory**a  >  **Groups**  >  **expiración**de grupos de Azure Active Directory. Aquí puede establecer la vigencia predeterminada del grupo y especificar la antelación con la que desea que las notificaciones de expiración primero y segundo vayan al propietario del grupo.

La duración del grupo se especifica en días y se puede establecer en 180, 365 o en un valor personalizado especificado por el usuario. El valor personalizado tiene que ser de al menos 30 días.

Si el grupo no tiene un propietario, los mensajes de correo electrónico de expiración Irán al administrador especificado.

Puede establecer la Directiva para todos los grupos, sólo para los grupos seleccionados, o bien desactivarla completamente seleccionando **ninguno**. Tenga en cuenta que actualmente no puede tener diferentes directivas para grupos diferentes.

![Captura de pantalla de la configuración de expiración de grupos en Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Funcionamiento de la expiración con la Directiva de retención

Si ha configurado una directiva de retención para grupos en el centro de seguridad y cumplimiento, la Directiva de expiración funciona perfectamente con la Directiva de retención. Cuando un grupo expira, las conversaciones del buzón y los archivos del sitio del grupo se conservan en el contenedor de retención para el número específico de días definido en la Directiva de retención. Sin embargo, los usuarios no verán el grupo o su contenido después de la expiración.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Cómo y cuándo un propietario del grupo aprende si sus grupos van a expirar

Solo se notificará a los propietarios del grupo por correo electrónico. Si el grupo se creó a través de Planner, SharePoint o cualquier otra aplicación, las notificaciones de expiración siempre se producirán por correo electrónico. Si el grupo se creó mediante Microsoft Teams, el propietario del grupo recibirá una notificación para renovar a través de la sección actividad. No se recomienda habilitar la expiración en un grupo si el propietario del grupo no tiene una dirección de correo electrónico válida.

Treinta días antes de que expire el grupo, los propietarios del grupo (o las direcciones de correo electrónico que ha especificado para los grupos que no tienen un propietario) recibirán un correo electrónico que les permitirá renovar fácilmente el grupo. Si no la renuevan, recibirán otra renovación de correo electrónico 15 días antes de la fecha de expiración. Si aún no lo han renovado, recibirán una notificación de correo electrónico más el día antes de la expiración.

Si, por algún motivo, ninguno de los propietarios o administradores renuevan el grupo antes de que expire, el administrador podrá seguir restaurando el grupo durante un máximo de 30 días después de la fecha de expiración. Para obtener información detallada, vea: [restore a Deleted Microsoft 365 Group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Contenido del grupo de archivado

Si tiene un grupo que ya no tiene previsto usar, pero desea conservar su contenido, vea [Archive Groups, Teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obtener información sobre cómo exportar información de los diferentes servicios de grupos.

## <a name="related-articles"></a>Artículos relacionados

[Información general sobre las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configurar la expiración de grupos de 365 de Microsoft](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
