---
title: Directiva de expiración de grupo de Microsoft 365
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
description: Obtenga información sobre las directivas de expiración de grupos de Microsoft 365.
ms.openlocfilehash: 8232e7df2a8390b905386773ed0656eb8239d5c5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920921"
---
# <a name="microsoft-365-group-expiration-policy"></a>Directiva de expiración de grupo de Microsoft 365

Con el aumento del uso de grupos de Microsoft 365 y Microsoft Teams, los administradores y los usuarios necesitan una forma de limpiar grupos y equipos sin usar. Una directiva de expiración de grupos de Microsoft 365 puede ayudar a quitar grupos inactivos del sistema y a limpiar las cosas.

Cuando un grupo expira, también se eliminan todos los servicios asociados (el buzón, Planner, sitio de SharePoint, equipo, etc.).

Cuando un grupo expira es "eliminado temporalmente", lo que significa que todavía se puede recuperar durante un máximo de 30 días.

Los administradores pueden especificar un período de expiración y se eliminará cualquier grupo inactivo que llegue al final de ese período y no se renueve. (Esto incluye equipos archivados). El período de expiración comienza cuando se crea el grupo o en la fecha en que se renovó por última vez. Los propietarios del grupo se enviarán automáticamente un correo electrónico antes de la expiración que les permita renovar el grupo para otro intervalo de expiración. Los usuarios de Teams verán notificaciones persistentes en Teams.

Los grupos que se usan activamente se renuevan automáticamente. Cualquiera de las siguientes acciones renovará automáticamente un grupo:
- SharePoint: ver, editar, descargar, mover, compartir o cargar archivos. (Ver una página de SharePoint no cuenta como una acción para la renovación automática).
- Outlook: unirse a un grupo, leer o escribir un mensaje de grupo desde el grupo y, como un mensaje (Outlook en la web).
- Teams: visitar un canal de equipos.

> [!IMPORTANT]
> Al cambiar la directiva de expiración, el servicio vuelve a calcular la fecha de expiración de cada grupo. Siempre comienza a contar desde la fecha en que se creó el grupo y, a continuación, aplica la nueva directiva de expiración.

Es importante saber que la expiración está desactivada de forma predeterminada. Los administradores tienen que habilitarlo para su organización si quieren usarlo.

> [!NOTE]
> La configuración y el uso de la directiva de expiración para grupos de Microsoft 365 requiere que poseas, pero no necesariamente, las licencias de Azure AD Premium para los miembros de todos los grupos a los que se aplica la directiva de expiración. Para obtener más información, [vea Introducción a Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>¿Quién puede configurar y usar la directiva de expiración de grupos de Microsoft 365?

|Role|Qué pueden hacer|
|---------|---------|
|Administrador global de Office 365 (en Azure, administrador de la compañía), administrador de usuarios|Cree, lea, actualice o elimine la configuración de directiva de expiración de grupos de Microsoft 365.|
|Usuario|Renovar o [restaurar](/azure/active-directory/users-groups-roles/groups-restore-deleted) un grupo de Microsoft 365 de su propiedad|

## <a name="how-to-set-the-expiration-policy"></a>Cómo establecer la directiva de expiración

Como se mencionó anteriormente, la expiración está desactivada de forma predeterminada. Un administrador tendrá que habilitar la directiva de expiración y establecer las propiedades para que su efecto. Para habilitarlo, vaya a **Expiración de grupos de Azure Active Directory**  >    >  . Aquí puede establecer la duración predeterminada del grupo y especificar con qué antelación desea que la primera y la segunda notificación de expiración vayan al propietario del grupo.

La duración del grupo se especifica en días y se puede establecer en 180, 365 o en un valor personalizado que especifique. El valor personalizado debe ser de al menos 30 días.

Si el grupo no tiene un propietario, los correos electrónicos de expiración irán al administrador especificado.

Puede establecer la directiva para todos los grupos, solo los grupos seleccionados o desactivarla completamente **seleccionando Ninguno**. Tenga en cuenta que actualmente no puede tener directivas diferentes para diferentes grupos.

![Captura de pantalla de la configuración de expiración de grupos en Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Cómo funciona la expiración con la directiva de retención

Si ha configurado una directiva de retención para grupos en el Centro de seguridad y cumplimiento, la directiva de expiración funciona sin problemas con la directiva de retención. Cuando un grupo expira, las conversaciones y los archivos del buzón del grupo en el sitio de grupo se conservan en el contenedor de retención durante el número específico de días definido en la directiva de retención. Sin embargo, los usuarios no verán el grupo ni su contenido después de expirar.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Cómo y cuándo el propietario de un grupo aprende si sus grupos van a expirar

Los propietarios del grupo solo recibirán una notificación por correo electrónico. Si el grupo se creó a través de Planner, SharePoint o cualquier otra aplicación, las notificaciones de expiración siempre se enviarán por correo electrónico. Si el grupo se creó a través de Teams, el propietario del grupo recibirá una notificación para renovarlo a través de la sección de actividad. No se recomienda habilitar la expiración en un grupo si el propietario del grupo no tiene una dirección de correo electrónico válida.

Treinta días antes de que expire el grupo, los propietarios del grupo (o las direcciones de correo electrónico especificadas para grupos que no tienen un propietario) recibirán un correo electrónico que les permitirá renovar fácilmente el grupo. Si no lo renuevan, recibirán otro correo electrónico de renovación 15 días antes de la expiración. Si aún no lo han renovado, recibirán una notificación de correo electrónico más el día antes de la expiración.

Si por alguna razón ninguno de los propietarios o administradores renueva el grupo antes de que expire, el administrador puede restaurar el grupo hasta 30 días después de la expiración. Para obtener más información, [vea: Restaurar un grupo de Microsoft 365 eliminado.](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)

## <a name="archiving-group-contents"></a>Contenido del grupo de archivado

Si tiene un grupo que ya no tiene previsto usar, pero desea conservar su contenido, consulte Grupos de archivo, equipos y [Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obtener información sobre cómo exportar información de los distintos servicios de grupos.

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Información general sobre las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configurar la expiración de grupos de Microsoft 365](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)