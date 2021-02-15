---
title: Interacciones de configuración entre grupos de Microsoft 365, Teams y SharePoint
ms.reviewer: ''
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
description: Obtenga información sobre las interacciones de configuración entre grupos de Microsoft 365, Teams y SharePoint
ms.openlocfilehash: 23ef7a316417109ae51c221f1a25524dea3abeca
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613671"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Interacciones de configuración entre grupos de Microsoft 365, Teams y SharePoint

Algunas opciones de configuración de Grupos de Microsoft 365, Microsoft Teams y SharePoint en Microsoft 365, especialmente relacionadas con el uso compartido y la creación de grupos o equipos y sitios de SharePoint, se superponen entre sí. En este artículo se proporcionan descripciones de estas interacciones y procedimientos recomendados para trabajar con esta configuración.

![Diagrama de Venn de características de SharePoint, Teams y grupos](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Efectos de la configuración de SharePoint en grupos y equipos

|Configuración de SharePoint|Description|Efecto en grupos de Microsoft 365 y Teams|Recomendación|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Uso compartido externo para la organización y el sitio|Determina si se pueden compartir sitios, archivos y carpetas con personas ajenas a la organización.|Si la configuración de SharePoint, grupos y Teams no coincide, es posible que los invitados del equipo no puedan acceder al sitio o que se produzca un acceso externo inesperado.|Al cambiar la configuración de uso compartido, compruebe la configuración de grupos, la configuración de Teams y la configuración del sitio de SharePoint para los sitios de grupo conectados a grupos.<br><br> Ver [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Dominio permitido/bloqueado|Permite o impide que el contenido se comparta con dominios especificados.|Los grupos y Teams no reconocen listas de permitidos o bloqueados de SharePoint. Los usuarios de dominios no permitidos en SharePoint podrían obtener acceso a sitios o contenido de SharePoint a través de un equipo.|Administre juntos listas de dominios permitidos y bloqueados para Azure AD y SharePoint. Cree un proceso de gobierno en toda la organización para permitir y bloquear dominios.<br><br>Ver [la configuración de dominio de SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) y la configuración de dominio de Azure [AD](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Permitir que solo los usuarios en grupos de seguridad específicos compartan externamente|Especifica grupos de seguridad que pueden compartir sitios, carpetas y archivos de SharePoint externamente.|Esta configuración no impide que los propietarios de equipos compartan equipos externamente. Los invitados de equipo tienen acceso al sitio de SharePoint asociado.||
|Configuración de uso compartido de sitios de SharePoint|Determina quién puede compartir el sitio directamente fuera de la pertenencia al equipo. Esto lo configura el equipo o el propietario del sitio.|Esta configuración no afecta directamente al equipo, pero puede permitir que los usuarios se agregan a un sitio y no tienen acceso al equipo en sí o a otros recursos de Teams.|Considere la posibilidad de usar esta configuración para limitar el uso compartido del sitio directamente y administrar el acceso al sitio a través del equipo.|
|Permitir a los usuarios crear sitios desde la página de inicio de SharePoint y OneDrive|Especifica si los usuarios pueden crear nuevos sitios de SharePoint.|Si esta configuración está desactivada, los usuarios aún pueden crear sitios de grupo conectados mediante la creación de un equipo.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Los efectos de la configuración de grupos en los equipos

|Configuración de grupos de Microsoft 365|Description|Efecto en Teams|Recomendación|
|:---------------------------|:----------|:--------------|:-------------|
|Directivas de nomenclatura|Especifica prefijos y sufijos de nombre de grupo y palabras bloqueadas para la creación de grupos|Las directivas se aplican a los usuarios que crean equipos.||
|Acceso de invitado de grupo|Especifica si se pueden agregar a grupos personas fuera de la organización.|Si los grupos o la configuración de uso compartido de invitados de Teams están desactivadas, el equipo no se puede compartir con invitados.|Al cambiar la configuración de uso compartido de invitados, compruebe la configuración de Teams, Grupos y el sitio de SharePoint asociado con el equipo.<br><br> Ver [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Creación de grupos por grupo de seguridad|Los grupos solo los pueden crear los miembros de un grupo de seguridad específico.|Los usuarios que no sean miembros del grupo de seguridad no podrán crear un equipo.|Asegúrese de que el proceso para solicitar un grupo incluye instrucciones para solicitar un equipo o un sitio de SharePoint.|
|Directiva de expiración de grupo|Especifica un período de tiempo después del cual los grupos que no se usan activamente se eliminarán automáticamente.|Cuando se elimina el grupo, también se eliminan el equipo y el sitio de SharePoint asociado. Se conserva el contenido protegido por directivas de retención.|Use directivas de expiración para evitar la expansión de equipos, grupos y sitios que no se usan.|

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear un plan de gobierno de colaboración](collaboration-governance-first.md)

[Colaborar con personas ajenas a la organización](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Administrar la creación de sitios en SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)
