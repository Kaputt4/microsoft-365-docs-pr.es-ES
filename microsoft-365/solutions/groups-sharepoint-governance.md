---
title: Interacciones de configuración entre grupos de Microsoft 365 y SharePoint
ms.reviewer: mmclean
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
description: Obtenga información sobre las interacciones de configuración entre grupos de Microsoft 365 y SharePoint
ms.openlocfilehash: a00e863fead8e74cf0f169471ebb36f9539ed103
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613495"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interacciones de configuración entre grupos de Microsoft 365 y SharePoint

Algunas opciones de configuración de Grupos de Microsoft 365 y SharePoint en Microsoft 365, especialmente relacionadas con el uso compartido y la creación de grupos y sitios de grupo, se superponen entre sí. En este artículo se proporcionan descripciones de estas interacciones y procedimientos recomendados para trabajar con esta configuración.

![Diagrama de Venn de características de SharePoint, Yammer y grupos](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Efectos de la configuración de SharePoint en grupos de Microsoft 365

|Configuración de SharePoint|Description|Efecto en grupos de Microsoft 365|Recomendación|
|:-----------------|:----------|:-----------------------------|:-------------|
|Uso compartido externo para la organización y el sitio|Determina si se pueden compartir sitios, archivos y carpetas con personas ajenas a la organización.|Si la configuración de SharePoint y grupos no coincide, es posible que los invitados del grupo no puedan acceder al sitio o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, compruebe la configuración de grupos y la configuración del sitio de SharePoint para los sitios de grupo conectados a grupos.<br><br>Vea [Colaborar con invitados en un sitio.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Dominio permitido/bloqueado|Permite o impide que el contenido se comparta con dominios especificados.|Los grupos no reconocen listas de permitidos o bloqueados de SharePoint. Los usuarios de dominios no permitidos en SharePoint podrían obtener acceso a SharePoint a través de un grupo.|Administre juntos listas de dominios permitidos y bloqueados para Azure AD y SharePoint. Cree un proceso de gobierno en toda la organización para permitir y bloquear dominios.<br><br>Ver [la configuración de dominio de SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) y la configuración de dominio de Azure [AD](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Permitir que solo los usuarios en grupos de seguridad específicos compartan externamente|Especifica grupos de seguridad que pueden compartir sitios, carpetas y archivos externamente.|Esta configuración no afecta a los propietarios de grupos que comparten grupos externamente. Los invitados de grupo tienen acceso al sitio de SharePoint asociado.||
|Configuración de uso compartido de sitios de SharePoint|Determina quién puede compartir el sitio directamente fuera de la pertenencia a grupos. Esto lo configura el propietario del sitio o grupo.|Esta configuración no afecta directamente al grupo, pero puede permitir que los usuarios se puedan agregar a un sitio y no tengan acceso a otros recursos del grupo.|Considere la posibilidad de usar esta opción para limitar el uso compartido del sitio directamente y administrar el acceso al sitio a través del grupo.|
|Permitir a los usuarios crear sitios desde la página de inicio de SharePoint y OneDrive|Especifica si los usuarios pueden crear nuevos sitios de SharePoint.|Si esta configuración está desactivada, los usuarios aún pueden crear sitios de grupo conectados a grupos mediante la creación de un grupo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Efectos de la configuración de grupos de Microsoft 365 en SharePoint

|Configuración de grupos de Microsoft 365|Description|Efecto en SharePoint|Recomendación|
|:---------------------------|:----------|:-------------------|:-------------|
|Directivas de nomenclatura|Especifica prefijos y sufijos de nombre de grupo y palabras bloqueadas para la creación de grupos|Las directivas se aplican a los usuarios que crean sitios de grupo conectados a grupos, pero no a sitios de comunicación o sitios con otras plantillas.|Cree instrucciones de nomenclatura independientes para los sitios de comunicación si es necesario.|
|Acceso de invitado de grupo|Especifica si se pueden agregar a grupos personas fuera de la organización.|Si la configuración de SharePoint y grupos no coincide, es posible que los invitados del grupo no puedan acceder al sitio o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, compruebe la configuración de grupos y la configuración del sitio de SharePoint para los sitios de grupo conectados a grupos.<br><br>Ver [Colaborar con invitados en un sitio](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Creación de grupos por grupo de seguridad|Los grupos solo los pueden crear los miembros de un grupo de seguridad específico.|Los usuarios que no sean miembros del grupo de seguridad no podrán crear un sitio de grupo conectado a un grupo.|Asegúrese de que el proceso para solicitar un grupo incluye instrucciones para solicitar un sitio.|
|Directiva de expiración de grupo|Especifica un período de tiempo después del cual los grupos que no se usan activamente se eliminarán automáticamente.|Cuando se elimina el grupo, también se elimina el sitio de SharePoint asociado. Se conserva el contenido protegido por directivas de retención.|Use directivas de expiración para evitar la expansión de sitios y grupos no usados.|

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear un plan de gobierno de colaboración](collaboration-governance-first.md)

[Colaborar con personas ajenas a la organización](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Administrar la creación de sitios en SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)