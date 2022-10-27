---
title: Información general de los grupos de Microsoft 365 para administradores
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Con Grupos de Microsoft 365, puede impulsar el trabajo en equipo en Microsoft 365 proporcionando a un grupo de personas acceso a una colección de recursos compartidos.
ms.openlocfilehash: a3501217e90d7b131621abae95450899b0b835a1
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68720380"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Información general de los grupos de Microsoft 365 para administradores

Microsoft 365 es el servicio de pertenencia fundamental que impulsa todo el trabajo en equipo en Microsoft 365. Con los grupos de Microsoft 365, puede conceder acceso a un grupo de personas a un conjunto de recursos compartidos. Estos recursos incluyen:

- Una bandeja de Outlook compartida
- Un calendario compartido
- Una biblioteca de documentos de SharePoint
- Un organizador
- Un bloc de notas de OneNote
- Power BI
- Yammer (si el grupo se creó a partir de Yammer)
- Un equipo (si el grupo se creó a partir de Teams)
- Guía básica (si tiene Project para la web)
- Stream

Con un grupo de Microsoft 365, no es necesario asignar manualmente permisos a cada uno de estos recursos. Agregar personas al grupo automáticamente les da los permisos que necesitan.

Cualquier usuario puede crear un grupo a menos que [limite la creación de grupos a un conjunto específico de personas](../../solutions/manage-creation-of-groups.md). Si limita la creación de grupos, los usuarios que no puedan crear grupos no podrán crear sitios de SharePoint, Planners, equipos, calendarios de grupos de Outlook, grupos de Stream, grupos de Yammer, bibliotecas compartidas en OneDrive o áreas de trabajo compartidas de Power BI. Estos servicios requieren que las personas que los crean puedan crear un grupo. Los usuarios pueden seguir participando en actividades de grupo, como la creación de tareas en Planner o el chat de Teams, siempre que sean miembros del grupo.

Los grupos tienen los siguientes roles:

- **Propietarios** : los propietarios de grupos pueden agregar o quitar miembros y tener permisos únicos, como la posibilidad de eliminar conversaciones de la bandeja de entrada compartida o cambiar diferentes configuraciones sobre el grupo. Los propietarios del grupo pueden cambiar el nombre del grupo, actualizar la descripción o la imagen, y mucho más.
- **Miembros** : los miembros pueden tener acceso a todo el grupo, pero no pueden cambiar la configuración del grupo. De forma predeterminada, los miembros del grupo pueden invitar a los invitados a unirse a su grupo, aunque puede [controlar esa configuración](manage-guest-access-in-groups.md).
- **Invitados** : los invitados de grupo son miembros que no pertenecen a la organización.

Solo los administradores globales, los administradores de usuarios y los administradores de grupos pueden crear y administrar grupos en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Centro de administración de Microsoft 365</a>. No puede ser un administrador delegado (por ejemplo, un consultor que sea un administrador en nombre de alguien).

Como administrador, puede:

- [Especificar quién puede crear grupos](../../solutions/manage-creation-of-groups.md)
- [Creación de una directiva de nomenclatura para grupos de la organización](../../solutions/groups-naming-policy.md)
- [Elección del dominio que se va a usar al crear un grupo](../../solutions/choose-domain-to-create-groups.md)
- [Administrar el acceso de invitado a grupos](manage-guest-access-in-groups.md)
- [Recuperar un grupo eliminado](restore-deleted-group.md) (dentro de los 30 días posteriores a la eliminación)

Si prefiere una manera más automatizada de administrar el ciclo de vida de los grupos de Microsoft 365, puede usar directivas de expiración para expirar grupos en un intervalo de tiempo específico. Los propietarios del grupo recibirán un correo electrónico 30, 15 y 1 día antes de la expiración del grupo que les permite renovar el grupo si todavía es necesario. Consulte: [Directiva de expiración de grupos de Microsoft 365](../../solutions/microsoft-365-groups-expiration-policy.md).

Puede administrar los grupos desde el Centro de administración de Microsoft 365 o [mediante PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md).

Si tiene muchos usuarios, como en una gran empresa o empresa, es posible que tenga muchos usuarios que creen grupos para diversos fines. Se recomienda encarecidamente que revise [Planear la gobernanza en grupos de Microsoft 365](../../solutions/collaboration-governance-overview.md) para conocer los procedimientos recomendados.

## <a name="group-limits"></a>Límites de grupo

Los límites siguientes se aplican a Grupos de Microsoft 365:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que puede crear un administrador|No hay límites específicos del grupo de Microsoft 365. Hay un límite general de objetos de Azure AD específico para cada organización. Un administrador de Azure AD que pueda administrar grupos de la organización puede crear un número ilimitado de grupos de Microsoft 365 hasta el límite de objetos de Azure AD. Consulte [Límites y restricciones del servicio AAD](/active-directory/enterprise-users/directory-service-limits-restrictions).|
|Número de miembros|Más de 1000, aunque solo 1000 pueden acceder a las conversaciones de grupo simultáneamente. <br>Los usuarios pueden observar retrasos al acceder al calendario y las conversaciones en grupos grandes en Outlook.|
|Número de grupos de los que un usuario puede ser miembro|7,000|
|Almacenamiento de archivos.|1 Terabyte + 10 GB por usuario suscrito + cualquier otro almacenamiento comprado. Puede comprar una cantidad ilimitada de almacenamiento adicional.|
|Tamaño del buzón de grupo|50 GB|


La administración de los grupos de Microsoft 365 es más eficaz cuando se dispone de información accionable sobre el uso de grupos. El Centro de administración de Microsoft 365 tiene una herramienta de informes que le permite ver el uso del almacenamiento, cuántos grupos activos tiene y cómo los usuarios usan los grupos. Consulte: [Informes de Microsoft 365 en el Centro de administración](../activity-reports/office-365-groups.md) para obtener más información.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Puede crear etiquetas de confidencialidad que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Con las etiquetas de confidencialidad, puede configurar: 

- Privacidad (pública o privada)
- Acceso de usuarios externos
- Acceso a dispositivos no administrados

Por ejemplo, puede crear una etiqueta denominada *Extremadamente confidencial* y especificar que cualquier grupo creado con esta etiqueta será privado y no permitirá usuarios externos. Cuando los usuarios de su organización seleccionan esta etiqueta durante la creación del grupo, el grupo se establecerá en privado y no se permitirá que los miembros del grupo agreguen usuarios externos al grupo.

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad. 

Para obtener información sobre cómo crear, administrar y usar etiquetas de confidencialidad, consulte [Uso de etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../../compliance/sensitivity-labels-teams-groups-sites.md).

## <a name="which-microsoft-365-plans-include-groups"></a>¿Qué planes de Microsoft 365 incluyen grupos?

Cualquier suscripción de Microsoft 365 que tenga Exchange Online y SharePoint Online admitirá grupos. Esto incluye los planes Business Essentials y Business Premium, y los planes Enterprise E1, E3 y E5. El grupo toma las licencias de la persona que crea el grupo (también conocido como el "organizador" del grupo). Siempre que el organizador tenga la licencia adecuada para las características que quiera que tenga el grupo, esa licencia se transmitirá al grupo.

> [!NOTE]
> Para obtener más información sobre las familias de servicios y los planes de Microsoft 365, consulte [Opciones de plan de Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Si tiene un plan solo de Exchange, puede obtener la bandeja de entrada compartida y las características de calendario compartido de los grupos en Outlook, pero no obtendrá la biblioteca de documentos, Planner ni ninguna de las otras funcionalidades.

Los grupos de Microsoft 365 funcionan con Azure Active Directory. Las características de grupos que obtenga dependerán de la suscripción de Azure Active Directory que tenga y de las licencias que se asignen al organizador del grupo.

> [!IMPORTANT]
> Para todas las características de grupos, si tiene una suscripción a Azure AD Premium, los usuarios pueden unirse al grupo independientemente de que tengan asignada una licencia de AAD P1. No se aplica la licencia.
> Periódicamente generaremos informes de uso que le indicarán qué usuarios faltan una licencia y que necesitan uno asignado para cumplir con los requisitos de licencia. Por ejemplo, supongamos que un usuario no tiene una licencia y se agrega a un grupo donde se aplica la directiva de nomenclatura. El informe le marcará que necesitan una licencia.

## <a name="related-content"></a>Contenido relacionado

[Más información sobre Grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (artículo)\
[Actualizar listas de distribución a Grupos de Microsoft 365](../manage/upgrade-distribution-lists.md) (artículo)\
[Administración de Grupos de Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artículo)\
[Límites de SharePoint Online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (artículo)\
[Organización de grupos y canales en Microsoft Stream](/stream/groups-channels-organization) (artículo)
