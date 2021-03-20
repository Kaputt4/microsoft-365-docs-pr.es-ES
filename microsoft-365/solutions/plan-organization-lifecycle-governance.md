---
title: Planear el gobierno de la organización y el ciclo de vida para grupos de Microsoft 365 y Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Información sobre las opciones de gobierno del ciclo de vida para herramientas de colaboración en Microsoft 365
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907933"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planear el gobierno de la organización y el ciclo de vida para grupos de Microsoft 365 y Microsoft Teams

Los grupos de Microsoft 365 tienen un amplio conjunto de herramientas para implementar las capacidades de gobierno que requiere la organización. 

En la siguiente sección se describen las capacidades, se recomiendan los procedimientos recomendados y se proporcionan instrucciones para hacer las preguntas adecuadas para determinar los requisitos de gobierno y cómo cumplirlas.

## <a name="control-who-can-create-microsoft-365-groups"></a>Controlar quién puede crear grupos de Microsoft 365

Los usuarios finales pueden crear grupos desde varios puntos finales, incluidos Outlook, SharePoint, Teams y otros entornos.

![image desc](../media/04.png)

Recomendamos encarecidamente el autoservicio para habilitar a los propietarios de grupos y ayudar a los usuarios a realizar su trabajo con más facilidad. Limitar la creación de grupos y equipos puede ralentizar la productividad de los usuarios, ya que muchos servicios de Microsoft 365 requieren la creación de grupos para que el servicio funcione.

Tenga en cuenta las siguientes opciones de gobierno para la creación de grupos:

- Para limitar la expansión de grupos, use directivas de expiración [de grupos](microsoft-365-groups-expiration-policy.md) para eliminar automáticamente los grupos que no se están utilizando.
- Limitar la creación de grupos a miembros de grupos de [seguridad](/azure/active-directory/users-groups-roles/groups-create-rule) con pertenencia dinámica que contenga, por ejemplo, todos los empleados a tiempo completo.
- Limite la creación de grupos a un grupo de seguridad y exija a los usuarios que completen el aprendizaje en las directivas de uso de grupo de su organización para convertirse en miembros del grupo de seguridad.

Si desea limitar quién puede crear grupos, vea Administrar quién puede crear grupos de [Microsoft 365](manage-creation-of-groups.md) para obtener información sobre cómo configurar esto.

## <a name="group-delete-restore-and-archiving"></a>Eliminación, restauración y archivado de grupos

Cuando se elimina un grupo de Microsoft 365, se conserva de forma predeterminada durante 30 días. Este período de 30 días se denomina "eliminación temporal", ya que todavía estará a tiempo de restaurar el grupo. Después de los 30 días, el grupo y el contenido asociado se eliminarán permanentemente y no se podrán restaurar.

Si tiene directivas de retención para conservar el chat, los archivos o el correo, esos elementos se conservarán después de eliminar el grupo. Vea [Más información sobre las directivas de retención](../compliance/retention.md) para obtener más información.

Si desea eliminar un grupo pero conservar el contenido de uno o varios de los servicios conectados a grupos, consulte Grupos de archivos, equipos [y Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obtener información.

## <a name="group-naming-policy"></a>Directiva de nomenclatura de grupo

Una directiva de nomenclatura de grupos puede ayudarle a gobernar grupos de dos maneras:

- Se puede usar una directiva de nomenclatura de prefijos o sufijos para aplicar cadenas fijas o atributos de Azure AD al principio o al final de un nombre de grupo y su dirección de correo electrónico asociada. Al hacerlo, puede garantizar la inclusión de, por ejemplo, nombres de departamento o regiones en nombres de grupo.
- Una directiva de palabras bloqueadas puede garantizar que determinadas palabras, como los nombres de los ejecutivos, no se usan en los nombres de grupo.

Las directivas de nomenclatura se aplican cuando se crean grupos desde cualquiera de los servicios conectados a grupos.

Si decide usar directivas de nomenclatura para grupos, consulte [Microsoft 365 Groups naming policy](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Directiva de expiración de grupo

Puede especificar un período de expiración y se eliminará cualquier grupo que llegue al final de ese período y no se renueve. El período de expiración comienza cuando se crea el grupo o en la fecha en que se renovó por última vez.

Una vez establecidos los grupos para que expiren:
- Se notificará a los propietarios del grupo para que renueve el grupo a medida que se acerca la expiración.
- Los grupos activos se renuevan automáticamente.
- Se elimina cualquier grupo que no se renueve.
- Los propietarios del grupo o el administrador pueden restaurar cualquier grupo que se elimine en un plazo de 30 días.

Las directivas de expiración son una buena forma de limitar la expansión de grupos al garantizar que se eliminen los grupos que ya no están en uso. Si desea crear una directiva de expiración de grupo, vea Directiva de [expiración de grupo de Microsoft 365](microsoft-365-groups-expiration-policy.md).

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)