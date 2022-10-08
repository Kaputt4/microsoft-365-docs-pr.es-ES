---
title: Interacciones de configuración entre grupos de Microsoft 365, Teams y SharePoint
ms.reviewer: ''
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
description: Más información sobre las interacciones de configuración entre Grupos de Microsoft 365, Teams y SharePoint
ms.openlocfilehash: 6d66b7e84d922108e83e8fa3e045272c82fd8f51
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986342"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Interacciones de configuración entre grupos de Microsoft 365, Teams y SharePoint

Algunas opciones de configuración para Grupos de Microsoft 365, Microsoft Teams y SharePoint en Microsoft 365, especialmente relacionadas con el uso compartido y la creación de grupos o equipos y la creación de sitios de SharePoint, se superponen entre sí. En este artículo se proporcionan descripciones de estas interacciones y procedimientos recomendados para trabajar con esta configuración.

![Diagrama de Venn de características de SharePoint, Teams y grupos.](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Los efectos de la configuración de SharePoint en grupos y equipos

|Configuración de SharePoint|Descripción|Efecto en los grupos de Microsoft 365 y Teams|Recomendación|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Uso compartido externo para la organización y el sitio|Determina si los sitios, archivos y carpetas se pueden compartir con personas ajenas a la organización.|Si la configuración de SharePoint, grupos y Teams no coincide, es posible que se bloquee el acceso al sitio a los invitados del equipo o que se produzca un acceso externo inesperado.|Al cambiar la configuración de uso compartido, compruebe Configuración de grupos, Configuración de Teams y Configuración del sitio de SharePoint para sitios de equipo conectados a grupos.<br><br> Consulte [Colaborar con invitados en un equipo](./collaborate-as-team.md)|
|Permitir o bloquear dominios|Permite o impide que el contenido se comparta con dominios especificados.|Los grupos y Teams no reconocen listas de permitidos ni listas de bloqueo de SharePoint. Los usuarios de dominios no permitidos en SharePoint podrían obtener acceso a sitios o contenido de SharePoint a través de un equipo.|Administre listas de permitidos de dominio o listas de bloqueo para Azure AD y SharePoint juntos. Cree un proceso de gobernanza en toda la organización para permitir y bloquear dominios.<br><br>Consulte [Configuración de dominio de SharePoint](/sharepoint/restricted-domains-sharing) y [Configuración de dominio de Azure AD](/azure/active-directory/b2b/allow-deny-list)|
|Permitir que solo los usuarios en grupos de seguridad específicos compartan externamente|Especifica grupos de seguridad que pueden compartir sitios, carpetas y archivos de SharePoint externamente.|Esta configuración no impide que los propietarios del equipo compartan equipos externamente. Los invitados del equipo tienen acceso al sitio de SharePoint asociado.||
|Configuración de uso compartido de sitios de SharePoint|Determina quién puede compartir el sitio directamente fuera de la pertenencia al equipo. Esto lo configura el equipo o el propietario del sitio.|Esta configuración no afecta directamente al equipo, pero puede permitir que los usuarios se agreguen a un sitio y no tengan acceso al propio equipo ni a otros recursos de Teams.|Considere la posibilidad de usar esta configuración para limitar el uso compartido del sitio directamente y administrar el acceso al sitio a través del equipo.|
|Permitir a los usuarios crear sitios desde la página de inicio de SharePoint y OneDrive|Especifica si los usuarios pueden crear nuevos sitios de SharePoint.|Si esta configuración está desactivada, los usuarios pueden seguir creando sitios de equipo conectados a grupos mediante la creación de un equipo.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Los efectos de la configuración de grupos en los equipos

|Configuración de grupos de Microsoft 365|Descripción|Efecto en Teams|Recomendación|
|:---------------------------|:----------|:--------------|:-------------|
|Directivas de nomenclatura|Especifica prefijos y sufijos de nombre de grupo, y palabras bloqueadas para la creación de grupos|Las directivas se aplican a los usuarios que crean equipos.||
|Acceso de invitado de grupo|Especifica si se pueden agregar personas ajenas a la organización a grupos.|Si la configuración de uso compartido de invitados de Teams o grupos está desactivada, el equipo no se puede compartir con los invitados.|Al cambiar la configuración de uso compartido de invitados, compruebe la configuración de Teams, Grupos y el sitio de SharePoint asociado al equipo.<br><br> Consulte [Colaborar con invitados en un equipo](./collaborate-as-team.md)|
|Creación de grupos por grupo de seguridad|Los grupos solo los pueden crear los miembros de un grupo de seguridad específico.|Los usuarios que no sean miembros del grupo de seguridad no podrán crear un equipo.|Asegúrese de que el proceso para solicitar un grupo incluye instrucciones para solicitar un equipo o un sitio de SharePoint.|
|Directiva de expiración de grupo|Especifica un período de tiempo después del cual se eliminarán automáticamente los grupos que no se usan activamente.|Cuando se elimina el grupo, también se eliminan el equipo y el sitio de SharePoint asociado. El contenido protegido por directivas de retención se conserva.|Use directivas de expiración para evitar la expansión de equipos, grupos y sitios no utilizados.|

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Colaborar con personas ajenas a la organización](./collaborate-with-people-outside-your-organization.md)

[Administrar la creación de un sitio de SharePoint](/sharepoint/manage-site-creation)