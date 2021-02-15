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
ms.openlocfilehash: 5d5c15c13d46738ac9de701b5a39f47274b9f1e5
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094738"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Información general de los grupos de Microsoft 365 para administradores

Grupos de Microsoft 365 es el servicio de pertenencia fundamental que impulsa todo el trabajo en equipo en Microsoft 365. Con Grupos de Microsoft 365, puede proporcionar a un grupo de personas acceso a una colección de recursos compartidos. Estos recursos incluyen:

- Una bandeja de entrada compartida de Outlook
- Un calendario compartido
- Una biblioteca de documentos de SharePoint
- Un organizador
- Un bloc de notas de OneNote
- Power BI
- Yammer (si el grupo se creó a partir de Yammer)
- Un equipo (si el grupo se creó a partir de Teams)
- Guía básica (si tiene Project para la web)

Con un grupo de Microsoft 365, no tiene que asignar manualmente permisos a cada uno de estos recursos. Agregar personas al grupo automáticamente les da los permisos que necesitan.

Cualquier usuario puede crear un grupo a menos que limite la creación [de grupos a un conjunto específico de personas.](manage-creation-of-groups.md) Si limita la creación de grupos, los usuarios que no puedan crear grupos no podrán crear sitios, organizadores o equipos de SharePoint. Estos servicios requieren que las personas que los crean puedan crear un grupo. Los usuarios aún pueden participar en actividades de grupo, como crear tareas en Planner o usar el chat de Teams, siempre que sean miembros del grupo.

Los grupos tienen los siguientes roles:

- **Propietarios:** los propietarios del grupo pueden agregar o quitar miembros y tener permisos únicos, como la capacidad de eliminar conversaciones de la bandeja de entrada compartida o cambiar diferentes configuraciones sobre el grupo. Los propietarios del grupo pueden cambiar el nombre del grupo, actualizar la descripción o la imagen, etc.
- **Miembros:** los miembros pueden acceder a todo el grupo, pero no pueden cambiar la configuración del grupo. De forma predeterminada, los miembros del grupo pueden invitar a invitados a unirse al grupo, aunque puede [controlar esa configuración.](manage-guest-access-in-groups.md)
- **Invitados:** los invitados del grupo son miembros que son de fuera de la organización.

Solo los administradores globales, los administradores de usuarios y los administradores de grupos pueden crear y administrar grupos en el Centro de administración de Microsoft 365. No puede ser un administrador delegado (por ejemplo, un consultor que sea un administrador en nombre de alguien).

Como administrador, puede:

- [Especificar quién puede crear grupos](manage-creation-of-groups.md)
- [Crear una directiva de nomenclatura para grupos de la organización](groups-naming-policy.md)
- [Elegir qué dominio usar al crear un grupo](choose-domain-to-create-groups.md)
- [Administrar el acceso de invitado a grupos](manage-guest-access-in-groups.md)
- [Recuperar un grupo eliminado](restore-deleted-group.md) (dentro de los 30 días posteriores a la eliminación)

Si prefiere una forma más automatizada de administrar el ciclo de vida de los grupos de Microsoft 365, puede usar directivas de expiración para expirar grupos en un intervalo de tiempo específico. Los propietarios del grupo recibirán un correo electrónico 30, 15 y 1 día antes de la expiración del grupo que les permitirá renovar el grupo si aún es necesario. Vea: Directiva de expiración de [grupo de Microsoft 365.](office-365-groups-expiration-policy.md)

Puede administrar los grupos desde el Centro de administración de Microsoft 365 o [mediante PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

Si tiene muchos usuarios, como en una gran empresa o empresa, es posible que tenga muchos usuarios que creen grupos con diversos fines. Le recomendamos encarecidamente que revise los procedimientos recomendados para planear el gobierno en los grupos de [Microsoft 365.](plan-for-groups-governance.md)

## <a name="group-limits"></a>Límites de grupo

Los siguientes límites se aplican a los Grupos de Microsoft 365:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que un administrador puede crear|Hasta un límite de inquilino predeterminado de 500 K|
|Número de miembros|Más de 1.000, aunque solo 1.000 pueden acceder a las conversaciones de grupo simultáneamente. <br>Es posible que los usuarios notan retrasos al acceder al calendario y a las conversaciones de grupos grandes en Outlook.|
|Número de grupos de los que un usuario puede ser miembro|7,000|
|Almacenamiento de archivos.|1 Terabyte + 10 GB por usuario suscrito + cualquier otro almacenamiento comprado. Puede comprar una cantidad ilimitada de almacenamiento adicional.|
|Tamaño del buzón de grupo|50 GB|

El número máximo predeterminado de grupos de Microsoft 365 que una organización puede tener es 500.000. Para superar el límite predeterminado, debe ponerse en contacto con el Soporte técnico de Microsoft. Para obtener más información sobre los límites de Grupos de Microsoft 365, vea Grupos de [Microsoft 365: ayuda para administradores.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

La administración de los grupos de Microsoft 365 es más eficaz cuando se tiene información que puede actuar sobre el uso de grupos. El Centro de administración de Microsoft 365 tiene una herramienta de informes que le permite ver el uso de almacenamiento, cuántos grupos activos tiene y cómo los usuarios usan los grupos. Vea: [Informes de Microsoft 365 en el centro de administración](../activity-reports/office-365-groups.md) para obtener más información.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Puede crear etiquetas de confidencialidad que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Con las etiquetas de confidencialidad, puede configurar: 

- Privacidad (pública o privada)
- Acceso de usuarios externos
- Acceso a dispositivos no administrados

Por ejemplo, puede crear una etiqueta denominada *Extremadamente* confidencial y especificar que cualquier grupo creado con esta etiqueta será privado y no permitirá usuarios externos. Cuando los usuarios de la organización seleccionan esta etiqueta durante la creación del grupo, el grupo se establecerá en privado y los miembros del grupo no podrán agregar usuarios externos al grupo.

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, estas ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad. 

Para obtener información sobre cómo crear, administrar y usar etiquetas de confidencialidad, vea Usar etiquetas de confidencialidad para proteger el contenido de Microsoft Teams, grupos de [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)y sitios de SharePoint.

## <a name="which-microsoft-365-plans-include-groups"></a>¿Qué planes de Microsoft 365 incluyen grupos?

Cualquier suscripción de Microsoft 365 que tenga Exchange Online y SharePoint Online admitirá grupos. Esto incluye los planes Business Essentials y Business Premium, y los planes Enterprise E1, E3 y E5. El grupo asume la licencia de la persona que crea el grupo (también conocido como "organizador" del grupo). Siempre que el organizador tenga la licencia adecuada para las características que quiera que tenga el grupo, esa licencia se transmitirá al grupo.

> [!NOTE]
> Para obtener más información sobre los planes y las familias de servicios de Microsoft 365, vea las opciones del [plan de Microsoft 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Si tiene un plan solo para Exchange, aún puede obtener las características de la bandeja de entrada compartida y del calendario compartido de los grupos en Outlook, pero no tendrá la biblioteca de documentos, Planner ni ninguna de las otras funciones.

Los grupos de Microsoft 365 funcionan con Azure Active Directory. Las características de grupos que obtenga dependerán de la suscripción de Azure Active Directory que tenga y de las licencias asignadas al organizador del grupo.

> [!IMPORTANT]
> Para todas las características de grupos, si tienes una suscripción a Azure AD Premium, los usuarios pueden unirse al grupo independientemente de si tienen asignada una licencia de AAD P1. Las licencias no se aplican.
> Periódicamente, generaremos informes de uso que le indican a qué usuarios les falta una licencia y necesita uno asignado para cumplir con los requisitos de licencia. Por ejemplo, supongamos que un usuario no tiene una licencia y se agrega a un grupo donde se aplica la directiva de nomenclatura. El informe le marcará que necesita una licencia.

## <a name="related-articles"></a>Artículos relacionados

[Más información sobre grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Actualizar listas de distribución a Grupos de Microsoft 365](../manage/upgrade-distribution-lists.md)

[Administrar grupos de Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Límites de SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
