---
title: Interacciones de configuración entre los grupos de Microsoft 365, Teams y SharePoint
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
description: Obtenga información sobre las interacciones de configuración entre los grupos de Microsoft 365, Teams y SharePoint
ms.openlocfilehash: 3a6d4e057f88410a8808ea133bf7e579d0041228
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377550"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Interacciones de configuración entre los grupos de Microsoft 365, Teams y SharePoint

Algunas opciones de configuración para Microsoft 365 grupos, Microsoft Teams y SharePoint en Microsoft 365, especialmente relacionadas con el uso compartido y la creación de sitios de grupo y grupo, se superponen entre sí. En este artículo se proporcionan descripciones de las interacciones y los procedimientos recomendados para trabajar con esta configuración.

![Diagrama de Venn de las características de SharePoint, Teams y Groups](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Efectos de la configuración de SharePoint en grupos y equipos

|Configuración de SharePoint|Description|Efecto en grupos y equipos de Microsoft 365|Recomendación|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Uso compartido externo de la organización y el sitio|Determina si se pueden compartir sitios, archivos y carpetas con personas de fuera de la organización.|Si la configuración de SharePoint, grupos y Teams no coincide, es posible que los invitados del equipo tengan bloqueado el acceso al sitio, o que se produzca un acceso externo inesperado.|Al cambiar la configuración de uso compartido, Compruebe la configuración de los grupos, la configuración de Teams y la configuración del sitio de SharePoint para los sitios de grupo conectados a un grupo.<br><br> Consulte [colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Permitir/bloquear dominio|Permite o impide que el contenido se comparta con los dominios especificados.|Los grupos y los equipos no reconocen las listas permitir o bloquear de SharePoint. Los usuarios de los dominios no permitidos en SharePoint podrían obtener acceso a contenido o sitios de SharePoint a través de un equipo.|Administre las listas de permitidos y bloqueados de dominio conjuntamente para Azure AD y SharePoint. Crear un proceso de gobierno para toda la organización para permitir y bloquear dominios.<br><br>Ver la [configuración de dominio de SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) y la configuración de dominio de [Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Permitir que solo los usuarios de grupos de seguridad específicos compartan externamente|Especifica grupos de seguridad que pueden compartir archivos, carpetas y sitios de SharePoint de forma externa.|Esta configuración no impide que los propietarios del equipo compartan equipos de forma externa. Los invitados del equipo tienen acceso al sitio de SharePoint asociado.||
|Configuración de uso compartido de sitios de SharePoint|Determina quién puede compartir el sitio directamente fuera de la pertenencia al equipo. El propietario del equipo o del sitio lo configura.|Esta configuración no afecta al equipo directamente, pero puede permitir que se agreguen usuarios a un sitio y no tengan acceso al equipo en sí o a otros recursos de Teams.|Considere la posibilidad de usar esta configuración para limitar el uso compartido del sitio de forma directa y administrar el acceso al sitio a través del equipo.|
|Permitir a los usuarios crear sitios desde la página de inicio de SharePoint y OneDrive|Especifica si los usuarios pueden crear nuevos sitios de SharePoint.|Si esta configuración está desactivada, los usuarios pueden crear sitios de grupo conectados a grupos mediante la creación de un equipo.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Los efectos de la configuración de grupos en Microsoft Teams

|Configuración de Microsoft 365 Groups|Description|Efecto en Microsoft Teams|Recomendación|
|:---------------------------|:----------|:--------------|:-------------|
|Directivas de nomenclatura|Especifica los prefijos y los sufijos de nombre de grupo, y las palabras bloqueadas para la creación de grupos|Las directivas se aplican a los usuarios que crean equipos.||
|Acceso de invitado de grupo|Especifica si las personas de fuera de la organización se pueden agregar a los grupos.|Si la configuración de uso compartido de invitado o grupos está desactivada, el equipo no se puede compartir con los invitados.|Al cambiar la configuración del uso compartido de invitado, Compruebe la configuración de Teams, grupos y el sitio de SharePoint asociado con el equipo.<br><br> Consulte [colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Creación de grupos por grupo de seguridad|Los grupos solo pueden ser creados por miembros de un grupo de seguridad específico.|Los usuarios que no son miembros del grupo de seguridad no podrán crear un equipo.|Asegúrese de que el proceso para solicitar un grupo incluye instrucciones para solicitar un equipo o un sitio de SharePoint.|
|Directiva de expiración de grupos|Especifica un período de tiempo tras el cual los grupos que no se usan de forma activa se eliminarán automáticamente.|Cuando se elimina el grupo, también se eliminan el equipo y el sitio de SharePoint asociado. Se conserva el contenido protegido por las directivas de retención.|Use directivas de expiración para evitar la proliferación de equipos, grupos y sitios que no se usen.|

## <a name="related-topics"></a>Temas relacionados

[Colaborar con personas fuera de la organización](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Administrar la creación de sitios en SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)
