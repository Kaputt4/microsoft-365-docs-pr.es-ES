---
title: Información general de los grupos de Microsoft 365 para administradores
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre grupos de Microsoft 365.
ms.openlocfilehash: 18cb37a4aae7a163d2e198194251abc727b48848
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910611"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Información general de los grupos de Microsoft 365 para administradores

Grupos de Microsoft 365 es el servicio de pertenencia fundamental que impulsa todo el trabajo en equipo en Microsoft 365. Con Grupos de Microsoft 365, puede proporcionar a un grupo de personas acceso a una colección de recursos compartidos. Estos recursos incluyen:

- Bandeja de entrada compartida de Outlook
- Un calendario compartido
- Una biblioteca de documentos de SharePoint
- Un organizador
- Un bloc de notas de OneNote
- Power BI
- Yammer (si el grupo se creó a partir de Yammer)
- Un equipo (si el grupo se creó desde Teams)
- Guía básica (si tiene Project para la web)
- Stream

Con un grupo de Microsoft 365, no tiene que asignar manualmente permisos a cada uno de estos recursos. Agregar personas al grupo automáticamente les da los permisos que necesitan.

Cualquier usuario puede crear un grupo a menos que [limite](../../solutions/manage-creation-of-groups.md)la creación de grupos a un conjunto específico de personas . Si limita la creación de grupos, los usuarios que no pueden crear grupos no podrán crear sitios de SharePoint, planners o equipos. Estos servicios requieren que las personas que los crean puedan crear un grupo. Los usuarios aún pueden participar en actividades de grupo, como crear tareas en Planner o usar el chat de Teams, siempre que sean miembros del grupo.

Los grupos tienen los siguientes roles:

- **Propietarios:** los propietarios de grupos pueden agregar o quitar miembros y tener permisos únicos, como la posibilidad de eliminar conversaciones de la bandeja de entrada compartida o cambiar diferentes configuraciones sobre el grupo. Los propietarios de grupos pueden cambiar el nombre del grupo, actualizar la descripción o la imagen, etc.
- **Miembros:** los miembros pueden tener acceso a todo el grupo, pero no pueden cambiar la configuración del grupo. De forma predeterminada, los miembros del grupo pueden invitar a los invitados a unirse a su grupo, aunque puede [controlar esa configuración](manage-guest-access-in-groups.md).
- **Invitados:** los invitados de grupo son miembros que son de fuera de la organización.

Solo los administradores globales, los administradores de usuarios y los administradores de grupos pueden crear y administrar grupos en el Centro de administración de Microsoft 365. No puede ser un administrador delegado (por ejemplo, un consultor que sea un administrador en nombre de alguien).

Como administrador, puede:

- [Especificar quién puede crear grupos](../../solutions/manage-creation-of-groups.md)
- [Crear una directiva de nomenclatura para grupos de la organización](../../solutions/groups-naming-policy.md)
- [Elegir qué dominio usar al crear un grupo](../../solutions/choose-domain-to-create-groups.md)
- [Administrar el acceso de invitado a grupos](manage-guest-access-in-groups.md)
- [Recuperar un grupo eliminado](restore-deleted-group.md) (dentro de los 30 días posteriores a la eliminación)

Si prefiere una forma más automatizada de administrar el ciclo de vida de los grupos de Microsoft 365, puede usar directivas de expiración para expirar grupos en un intervalo de tiempo específico. Los propietarios del grupo recibirán un correo electrónico 30, 15 y 1 día antes de la expiración del grupo que les permite renovar el grupo si aún es necesario. Vea: Directiva de expiración de grupo [de Microsoft 365](../../solutions/microsoft-365-groups-expiration-policy.md).

Puede administrar los grupos desde el Centro de administración de Microsoft 365 o [mediante PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md).

Si tiene muchos usuarios, como en una gran empresa o una empresa, puede que tenga muchos usuarios que creen grupos para diversos fines. Le recomendamos encarecidamente que revise [Plan for governance in Microsoft 365 groups](../../solutions/collaboration-governance-overview.md) para obtener los procedimientos recomendados.

## <a name="group-limits"></a>Límites de grupo

Los siguientes límites se aplican a grupos de Microsoft 365:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que un administrador puede crear|Límite de espacio empresarial predeterminado de 500 K|
|Número de miembros|Más de 1.000, aunque solo 1.000 pueden acceder a las conversaciones de grupo simultáneamente. <br>Es posible que los usuarios notan retrasos al acceder al calendario y a las conversaciones en grupos grandes en Outlook.|
|Número de grupos de los que un usuario puede ser miembro|7,000|
|Almacenamiento de archivos.|1 Terabyte + 10 GB por usuario suscrito + cualquier otro almacenamiento comprado. Puede comprar una cantidad ilimitada de almacenamiento adicional.|
|Tamaño del buzón de grupo|50 GB|

El número máximo predeterminado de grupos de Microsoft 365 que puede tener una organización es 500 000. Para superar el límite predeterminado, debe ponerse en contacto con el Soporte técnico de Microsoft. Para obtener más información sobre los límites de grupos de Microsoft 365, vea Grupos de [Microsoft 365 - Ayuda para administradores.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

La administración de los grupos de Microsoft 365 es más eficaz cuando se tiene información útil sobre el uso de grupos. El Centro de administración de Microsoft 365 tiene una herramienta de informes que le permite ver el uso del almacenamiento, cuántos grupos activos tiene y cómo los usuarios usan los grupos. Vea: [Informes de Microsoft 365 en el Centro de administración](../activity-reports/office-365-groups.md) para obtener más información.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Puede crear etiquetas de confidencialidad que los usuarios de su organización puedan establecer cuando creen un grupo de Microsoft 365. Con las etiquetas de confidencialidad, puede configurar: 

- Privacidad (pública o privada)
- Acceso de usuarios externos
- Acceso a dispositivos no administrados

Por ejemplo, puede crear una etiqueta denominada *Extremadamente* confidencial y especificar que cualquier grupo creado con esta etiqueta será privado y no permitirá usuarios externos. Cuando los usuarios de la organización seleccionan esta etiqueta durante la creación del grupo, el grupo se establecerá en privado y los miembros del grupo no podrán agregar usuarios externos al grupo.

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad. 

Para obtener información sobre cómo crear, administrar y usar etiquetas de confidencialidad, vea Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de [Microsoft 365](../../compliance/sensitivity-labels-teams-groups-sites.md)y sitios de SharePoint .

## <a name="which-microsoft-365-plans-include-groups"></a>¿Qué planes de Microsoft 365 incluyen grupos?

Cualquier suscripción de Microsoft 365 que tenga Exchange Online y SharePoint Online admitirá grupos. Esto incluye los planes Business Essentials y Business Premium, y los planes Enterprise E1, E3 y E5. El grupo asume las licencias de la persona que crea el grupo (también conocida como "organizadora" del grupo). Siempre que el organizador tenga la licencia adecuada para las características que quiera que tenga el grupo, esa licencia se transmitirá al grupo.

> [!NOTE]
> Para obtener más información acerca de los planes y las familias de servicios de Microsoft 365, vea Opciones de plan de [Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Si tiene un plan solo para Exchange, puede obtener las características de la bandeja de entrada compartida y del calendario compartido de los grupos en Outlook, pero no podrá obtener la biblioteca de documentos, Planner ni ninguna de las otras funcionalidades.

Los grupos de Microsoft 365 funcionan con Azure Active Directory. Las características de grupos que obtiene dependen de la suscripción de Azure Active Directory que tenga y de las licencias asignadas al organizador del grupo.

> [!IMPORTANT]
> Para todas las características de grupos, si tiene una suscripción a Azure AD Premium, los usuarios pueden unirse al grupo independientemente de si tienen o no una licencia de AAD P1 asignada. Las licencias no se aplican.
> Periódicamente, generaremos informes de uso que le indican qué usuarios no tienen una licencia y que necesitan uno asignado para cumplir con los requisitos de licencia. Por ejemplo, supongamos que un usuario no tiene una licencia y que se agrega a un grupo donde se aplica la directiva de nomenclatura. El informe marcará que necesitan una licencia.

## <a name="related-articles"></a>Artículos relacionados

[Información sobre grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Actualizar listas de distribución a grupos de Microsoft 365](../manage/upgrade-distribution-lists.md)

[Administrar grupos de Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)

[Límites de SharePoint Online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Organizar grupos y canales en Microsoft Stream](/stream/groups-channels-organization)