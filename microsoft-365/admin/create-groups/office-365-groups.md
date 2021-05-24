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
description: Con Microsoft 365, puede impulsar el trabajo en equipo en Microsoft 365, ya que proporciona a un grupo de personas acceso a una colección de recursos compartidos.
ms.openlocfilehash: f940872a3e4ba2aeeb62247c2898d5a4c0dec85f
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635755"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Información general de los grupos de Microsoft 365 para administradores

Microsoft 365 Los grupos son el servicio de pertenencia fundamental que impulsa todo el trabajo en equipo en Microsoft 365. Con Microsoft 365, puede proporcionar a un grupo de personas acceso a una colección de recursos compartidos. Estos recursos incluyen:

- Bandeja de Outlook compartida
- Un calendario compartido
- Una SharePoint de documentos
- Un organizador
- Un bloc de notas de OneNote
- Power BI
- Yammer (si el grupo se creó a partir de Yammer)
- Un equipo (si el grupo se creó a partir de Teams)
- Guía básica (si tiene Project para la web)
- Stream

Con un Microsoft 365, no tiene que asignar manualmente permisos a cada uno de estos recursos. Agregar personas al grupo automáticamente les da los permisos que necesitan.

Cualquier usuario puede crear un grupo a menos que [limite](../../solutions/manage-creation-of-groups.md)la creación de grupos a un conjunto específico de personas . Si limita la creación de grupos, los usuarios que no puedan crear grupos no podrán crear SharePoint, planners o equipos. Estos servicios requieren que las personas que los crean puedan crear un grupo. Los usuarios aún pueden participar en actividades de grupo, como crear tareas en Planner o usar Teams chat, siempre que sean miembros del grupo.

Los grupos tienen los siguientes roles:

- **Propietarios:** los propietarios de grupos pueden agregar o quitar miembros y tener permisos únicos, como la posibilidad de eliminar conversaciones de la bandeja de entrada compartida o cambiar diferentes configuraciones sobre el grupo. Los propietarios de grupos pueden cambiar el nombre del grupo, actualizar la descripción o la imagen, etc.
- **Miembros:** los miembros pueden tener acceso a todo el grupo, pero no pueden cambiar la configuración del grupo. De forma predeterminada, los miembros del grupo pueden invitar a los invitados a unirse a su grupo, aunque puede [controlar esa configuración](manage-guest-access-in-groups.md).
- **Invitados:** los invitados de grupo son miembros que son de fuera de la organización.

Solo los administradores globales, los administradores de usuarios y los grupos pueden crear y administrar grupos en el Microsoft 365 administración. No puede ser un administrador delegado (por ejemplo, un consultor que sea un administrador en nombre de alguien).

Como administrador, puede:

- [Especificar quién puede crear grupos](../../solutions/manage-creation-of-groups.md)
- [Crear una directiva de nomenclatura para grupos de la organización](../../solutions/groups-naming-policy.md)
- [Elegir qué dominio usar al crear un grupo](../../solutions/choose-domain-to-create-groups.md)
- [Administrar el acceso de invitado a grupos](manage-guest-access-in-groups.md)
- [Recuperar un grupo eliminado](restore-deleted-group.md) (dentro de los 30 días posteriores a la eliminación)

Si prefiere una forma más automatizada de administrar el ciclo de vida de los grupos de Microsoft 365, puede usar directivas de expiración para expirar grupos en un intervalo de tiempo específico. Los propietarios del grupo recibirán un correo electrónico 30, 15 y 1 día antes de la expiración del grupo que les permite renovar el grupo si aún es necesario. Vea: Microsoft 365 [de expiración de grupo](../../solutions/microsoft-365-groups-expiration-policy.md).

Puede administrar los grupos desde el centro de administración Microsoft 365 o [mediante PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md).

Si tiene muchos usuarios, como en una gran empresa o una empresa, puede que tenga muchos usuarios que creen grupos para diversos fines. Le recomendamos encarecidamente que revise [Plan for governance in Microsoft 365 groups](../../solutions/collaboration-governance-overview.md) para obtener procedimientos recomendados.

## <a name="group-limits"></a>Límites de grupo

Los siguientes límites se aplican a Microsoft 365 grupos:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que un administrador puede crear|Límite de espacio empresarial predeterminado de 500 K|
|Número de miembros|Más de 1.000, aunque solo 1.000 pueden acceder a las conversaciones de grupo simultáneamente. <br>Es posible que los usuarios notan retrasos al acceder al calendario y a las conversaciones en grupos grandes en Outlook.|
|Número de grupos de los que un usuario puede ser miembro|7,000|
|Almacenamiento de archivos.|1 Terabyte + 10 GB por usuario suscrito + cualquier otro almacenamiento comprado. Puede comprar una cantidad ilimitada de almacenamiento adicional.|
|Tamaño del buzón de grupo|50 GB|

El número máximo predeterminado de Microsoft 365 que puede tener una organización es 500 000. Para superar el límite predeterminado, debe ponerse en contacto con el Soporte técnico de Microsoft. Para obtener más información sobre Microsoft 365 de grupos, [vea Microsoft 365 Groups - Admin help](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

La administración de Microsoft 365 usuarios es más eficaz cuando se tiene información útil sobre el uso de grupos. El centro Microsoft 365 administración tiene una herramienta de informes que le permite ver el uso del almacenamiento, cuántos grupos activos tiene y cómo los usuarios usan los grupos. Vea: [Microsoft 365 informes en el Centro de administración](../activity-reports/office-365-groups.md) para obtener más información.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Puede crear etiquetas de confidencialidad que los usuarios de su organización puedan establecer al crear un grupo Microsoft 365 grupo. Con las etiquetas de confidencialidad, puede configurar: 

- Privacidad (pública o privada)
- Acceso de usuarios externos
- Acceso a dispositivos no administrados

Por ejemplo, puede crear una etiqueta denominada *Extremadamente* confidencial y especificar que cualquier grupo creado con esta etiqueta será privado y no permitirá usuarios externos. Cuando los usuarios de la organización seleccionan esta etiqueta durante la creación del grupo, el grupo se establecerá en privado y los miembros del grupo no podrán agregar usuarios externos al grupo.

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad. 

Para obtener información sobre cómo crear, administrar y usar etiquetas de confidencialidad, vea Usar etiquetas de confidencialidad para proteger el contenido de Microsoft Teams, Microsoft 365 grupos y [SharePoint de confidencialidad.](../../compliance/sensitivity-labels-teams-groups-sites.md)

## <a name="which-microsoft-365-plans-include-groups"></a>¿Microsoft 365 planes incluyen grupos?

Cualquier Microsoft 365 suscripción que tenga Exchange Online y SharePoint Online admitirán grupos. Esto incluye los planes Business Essentials y Business Premium y los Enterprise E1, E3 y E5. El grupo asume las licencias de la persona que crea el grupo (también conocida como "organizadora" del grupo). Siempre que el organizador tenga la licencia adecuada para las características que quiera que tenga el grupo, esa licencia se transmitirá al grupo.

> [!NOTE]
> Para obtener más información sobre Microsoft 365 y planes de servicio, vea [Microsoft 365 plan options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Si tiene un plan de solo Exchange, puede obtener las características de la bandeja de entrada compartida y del calendario compartido de los grupos en Outlook pero no podrá obtener la biblioteca de documentos, Planner ni ninguna de las otras funcionalidades.

Microsoft 365 grupos funcionan con Azure Active Directory. Las características de grupos que obtienes dependen Azure Active Directory suscripción que tienes y de qué licencias se asignan al organizador del grupo.

> [!IMPORTANT]
> Para todas las características de grupos, si tiene una suscripción a Azure AD Premium, los usuarios pueden unirse al grupo independientemente de si tienen o no una licencia de AAD P1 asignada. Las licencias no se aplican.
> Periódicamente, generaremos informes de uso que le indican qué usuarios no tienen una licencia y que necesitan uno asignado para cumplir con los requisitos de licencia. Por ejemplo, supongamos que un usuario no tiene una licencia y que se agrega a un grupo donde se aplica la directiva de nomenclatura. El informe marcará que necesitan una licencia.

## <a name="related-content"></a>Contenido relacionado

[Obtenga información sobre Microsoft 365 grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (artículo)\
[Actualizar listas de distribución a Microsoft 365 grupos](../manage/upgrade-distribution-lists.md) (artículo)\
[Administrar Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artículo)\
[SharePoint Online Limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (artículo)\
[Organizar grupos y canales en Microsoft Stream](/stream/groups-channels-organization) (artículo)