---
title: Planeamiento de la gobernanza de la organización y del ciclo de vida para grupos de Microsoft 365 y Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Acerca de las opciones de gobernanza del ciclo de vida para las herramientas de colaboración en Microsoft 365
ms.openlocfilehash: 5e5c112ecd13572c09252df88434443daa0c2005
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986496"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planeamiento de la gobernanza de la organización y del ciclo de vida para grupos de Microsoft 365 y Microsoft Teams

Los grupos de Microsoft 365 tienen un amplio conjunto de herramientas para implementar las funcionalidades de gobernanza que requiere su organización. 

En la sección siguiente se describen las funcionalidades, se recomiendan los procedimientos recomendados y se proporcionan instrucciones para formular las preguntas adecuadas para determinar los requisitos de gobernanza y cómo cumplirlas.

## <a name="control-who-can-create-microsoft-365-groups"></a>Controlar quién puede crear grupos de Microsoft 365

Los usuarios finales pueden crear grupos desde varios puntos de conexión, como Outlook, SharePoint, Teams y otros entornos.

![image desc.](../media/04.png)

Se recomienda encarecidamente el autoservicio para capacitar a los propietarios del grupo y ayudar a los usuarios a realizar su trabajo más fácilmente. Limitar la creación de grupos y equipos puede ralentizar la productividad de los usuarios porque muchos servicios de Microsoft 365 requieren que se creen grupos para que el servicio funcione.

Tenga en cuenta las siguientes opciones de gobernanza para la creación de grupos:

- Para limitar la expansión de grupos, use [directivas de expiración de grupos](microsoft-365-groups-expiration-policy.md) para eliminar automáticamente los grupos que no se usan.
- Limite la creación de grupos a los miembros de un [grupo de seguridad con pertenencia dinámica](/azure/active-directory/users-groups-roles/groups-create-rule) que contenga, por ejemplo, todos los empleados a tiempo completo.
- Limite la creación de grupos a un grupo de seguridad y exija a los usuarios que completen el entrenamiento en las directivas de uso de grupos de su organización para convertirse en miembros del grupo de seguridad.

Si desea limitar quién puede crear grupos, consulte [Administrar quién puede crear grupos de Microsoft 365](manage-creation-of-groups.md) para obtener información sobre cómo configurarlo.

## <a name="group-delete-restore-and-archiving"></a>Eliminación, restauración y archivado de grupos

Cuando se elimina un grupo de Microsoft 365, de forma predeterminada se conserva durante 30 días. Este período de 30 días se denomina "eliminación temporal", ya que todavía estará a tiempo de restaurar el grupo. Después de los 30 días, el grupo y el contenido asociado se eliminarán permanentemente y no se podrán restaurar.

Si tiene directivas de retención para conservar el chat, los archivos o el correo, esos elementos se conservarán después de eliminar el grupo. Consulte [Más información sobre las directivas de retención](../compliance/retention.md) para obtener más información.

Si desea eliminar un grupo, pero conservar el contenido de uno o varios de los servicios conectados al grupo, consulte [Grupos de archivos, equipos y Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obtener información.

## <a name="group-naming-policy"></a>Directiva de nomenclatura de grupos

Una directiva de nomenclatura de grupos puede ayudarle a controlar los grupos de dos maneras:

- Se puede usar una directiva de nomenclatura de prefijos o sufijos para aplicar cadenas fijas o atributos de Azure AD al principio o al final de un nombre de grupo y su dirección de correo electrónico asociada. Al hacerlo, puede garantizar la inclusión de, por ejemplo, nombres de departamento o regiones en los nombres de grupo.
- Una directiva de palabras bloqueadas puede garantizar que ciertas palabras, como los nombres de los ejecutivos, no se usen en los nombres de grupo.

Las directivas de nomenclatura se aplican cuando se crean grupos a partir de cualquiera de los servicios conectados a grupos.

Si decide usar directivas de nomenclatura para grupos, consulte [Grupos de Microsoft 365 directiva de nomenclatura](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Directiva de expiración de grupo

Puede especificar un período de expiración y cualquier grupo que llegue al final de ese período, y no se renueve, se eliminará. El período de expiración comenzará cuando se cree el grupo o en la fecha en que se renovó por última vez.

Una vez establecidos los grupos para que expiren:
- Se notifica a los propietarios del grupo que renueve el grupo a medida que se acerca la expiración.
- Los grupos activos se renuevan automáticamente.
- Se elimina cualquier grupo que no se renueve.
- Los propietarios del grupo o el administrador pueden restaurar cualquier grupo que se elimine en un plazo de 30 días.

Las directivas de expiración son una buena manera de limitar la expansión de grupos asegurándose de que se eliminen los grupos que ya no están en uso. Si desea crear una directiva de expiración de grupo, consulte [Grupos de Microsoft 365 directiva de expiración](microsoft-365-groups-expiration-policy.md).

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Quitar un antiguo empleado y proteger los datos](/microsoft-365/admin/add-users/remove-former-employee)
