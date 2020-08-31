---
title: Información general de los grupos de Microsoft 365 para administradores
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: Obtenga información sobre los grupos de 365 de Microsoft.
ms.openlocfilehash: 711ab7e7818b266d7cbdbe076e30355d29bc3eeb
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307270"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Información general de los grupos de Microsoft 365 para administradores

Microsoft 365 Groups es el servicio de pertenencia básico que dirige todo el trabajo en equipo en Microsoft 365. Con los grupos de Microsoft 365, puede conceder a un grupo de personas acceso a una colección de recursos de colaboración para que lo compartan los usuarios. Entre estos recursos se incluyen:

- Una bandeja de entrada de Outlook compartida
- Un calendario compartido
- Una biblioteca de documentos de SharePoint
- Un organizador
- Un bloc de notas de OneNote
- Power BI
- Yammer (si el grupo se creó desde Yammer)
- Un equipo (si el grupo se creó desde Microsoft Teams)
- Guía básica (si tiene Project para la web)

Con un grupo de Microsoft 365, no es necesario asignar manualmente permisos a cada uno de estos recursos, ya que agregar personas al grupo automáticamente les da los permisos que necesitan para las herramientas que proporciona el grupo.

Cualquier usuario puede crear un grupo a menos que [limite la creación de grupos a un conjunto específico de personas](manage-creation-of-groups.md). Tenga en cuenta que, si limita la creación de grupos, los usuarios que no pueden crear grupos no podrán crear sitios, diseñadores o equipos de SharePoint. Estos servicios requieren que los usuarios que los creen puedan crear un grupo. Los usuarios aún pueden participar en actividades de grupo, como la creación de tareas en Planner o mediante el chat de Teams, siempre que sean miembros del grupo.

Los grupos tienen los siguientes roles:

- **Propietarios** : los propietarios de los grupos pueden agregar o quitar miembros y tener permisos únicos, como la capacidad de eliminar conversaciones de la bandeja de entrada compartida o cambiar configuraciones distintas sobre el grupo. Los propietarios del grupo pueden cambiar el nombre del grupo, actualizar la descripción o la imagen, y más.
- **Los** miembros de pueden tener acceso a todo el grupo, pero no pueden cambiar la configuración del grupo. De forma predeterminada, los miembros del grupo pueden invitar a los invitados a unirse a su grupo, aunque puede [controlar esa configuración](manage-guest-access-in-groups.md).
- **Invitados: los** invitados del grupo son miembros de fuera de la organización.

Solo los administradores globales, los administradores de usuarios y los administradores de grupos pueden crear y administrar grupos en el centro de administración de Microsoft 365. No puede ser un administrador delegado (por ejemplo, un consultor que sea un administrador en nombre de alguien).

Como administrador, puede:

- [Especificar quién puede crear grupos](manage-creation-of-groups.md)
- [Crear una directiva de nomenclatura para los grupos de la organización](groups-naming-policy.md)
- [Elegir el dominio que se va a usar al crear un grupo](choose-domain-to-create-groups.md)
- [Administrar el acceso de invitado a grupos](manage-guest-access-in-groups.md)
- [Recuperar un grupo eliminado](restore-deleted-group.md) (en un plazo de 30 días después de la eliminación)

Si prefiere una forma más automatizada de administrar el ciclo de vida de los grupos de Microsoft 365, puede usar directivas de caducidad para que los grupos expiren en un intervalo de tiempo específico. Los propietarios del grupo recibirán un correo electrónico 30, 15 y 1 día antes de la expiración del grupo que les permite renovar fácilmente el grupo si sigue necesitando. Consulte: [Directiva de expiración de grupo 365 de Microsoft](office-365-groups-expiration-policy.md).

Puede administrar los grupos desde el centro de administración de Microsoft 365 o mediante [PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel).

Si tiene muchos usuarios, como en una corporación o empresa grande, es posible que tenga muchos usuarios que crean grupos con varios fines. Se recomienda encarecidamente que revise [Plan for Governance en Microsoft 365 Groups](plan-for-groups-governance.md) para conocer los procedimientos recomendados.

## <a name="group-limits"></a>Límites de grupo

Los siguientes límites se aplican a los grupos de Microsoft 365:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que puede crear un administrador|Hasta el límite de inquilino predeterminado de 500 k|
|Número de miembros|Más de 1.000, aunque solo 1.000 puede tener acceso a las conversaciones de grupo a la vez. <br>Es posible que los usuarios perciban retrasos al obtener acceso al calendario y a las conversaciones en grupos muy grandes en Outlook.|
|Número de grupos a los que puede pertenecer un usuario|1,000|
|Almacenamiento de archivos.|1 terabyte + 10 GB por usuario suscrito + almacenamiento adicional adquirido. Puede adquirir una cantidad ilimitada de almacenamiento adicional.|
|Tamaño del buzón de grupo|50 GB|

El número máximo predeterminado de grupos de Microsoft 365 que puede tener una organización es de 500.000. Para superar el límite predeterminado, debe ponerse en contacto con el soporte técnico de Microsoft. Para obtener más información sobre los límites de grupos de 365 de Microsoft, consulte [microsoft 365 Groups: ayuda de administración](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

La administración de los grupos de Microsoft 365 es más eficaz cuando tiene información que requiere la acción sobre el uso de los grupos. El centro de administración de Microsoft 365 tiene una herramienta de informes que le permite ver cosas como el uso del almacenamiento, cuántos grupos activos tiene e incluso cómo los usuarios usan los grupos. Consulte: [informes de Microsoft 365 en el centro de administración](../activity-reports/office-365-groups.md) para obtener más información.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Puede crear etiquetas de confidencialidad que los usuarios de su organización puedan establecer al crear un grupo de Microsoft 365. Con las etiquetas de confidencialidad, puede configurar: 

- Privacidad (pública o privada)
- Acceso de usuarios externos
- Acceso de dispositivos no administrados

Por ejemplo, puede crear una etiqueta denominada *extremadamente confidencial* y especificar que cualquier grupo que se cree con esta etiqueta será privado y no permitirá usuarios externos. Cuando los usuarios de la organización seleccionen esta etiqueta durante la creación del grupo, el grupo se establecerá en privado y no se permitirá que los miembros del grupo agreguen usuarios externos al grupo.

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, ya no estarán disponibles para los usuarios que crean grupos cuando las etiquetas de confidencialidad están habilitadas. 

Para obtener información sobre cómo crear, administrar y usar las etiquetas de confidencialidad, vea [usar las etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de 365 de Microsoft y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="which-microsoft-365-plans-include-groups"></a>¿Qué planes de Microsoft 365 incluyen grupos?

Cualquier suscripción a Microsoft 365 que tenga Exchange Online y SharePoint Online será compatible con grupos. Esto incluye los planes de empresa Essentials y empresa Premium, y los planes Enterprise E1, E3 y E5. El grupo toma la licencia de la persona que crea el grupo (también conocido como "organizador" del grupo). Siempre que el organizador tenga la licencia adecuada para las características que desee que tenga el grupo, dicha licencia se transmitirá al grupo.

> [!NOTE]
> Para obtener más información acerca de los planes y las familias de servicios de Microsoft 365, consulte [Opciones de plan de 365 de Microsoft](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Si tiene un plan de solo Exchange, todavía puede obtener las características de bandeja de entrada compartida y calendario compartido de los grupos en Outlook, pero no obtendrá la biblioteca de documentos, el programador ni ninguna de las demás funcionalidades.

Los grupos de Microsoft 365 funcionan con Azure Active Directory (AAD). Las características de grupos que obtengas dependen de qué suscripción de Azure Active Directory tiene y qué licencia o licencias se asignan al organizador del grupo.

> [!IMPORTANT]
> Para todas las características de grupos, si tiene una suscripción de Azure AD Premium, los usuarios pueden unirse al grupo independientemente de si tienen una licencia de AAD P1 asignada. No se aplican licencias.
> Periódicamente, se generarán informes de uso que indican a qué usuarios les falta una licencia y necesitan que se les asigne una para cumplir con los requisitos de licencia. Por ejemplo, supongamos que un usuario no tiene una licencia y se agrega a un grupo en el que se aplica la Directiva de nomenclatura. El informe se marcará para usted que necesita una licencia.

## <a name="related-articles"></a>Artículos relacionados

[Obtenga información sobre los grupos de 365 de Microsoft](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Actualizar listas de distribución a grupos de 365 de Microsoft](../manage/upgrade-distribution-lists.md)

[Administración de grupos de Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Límites de SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
