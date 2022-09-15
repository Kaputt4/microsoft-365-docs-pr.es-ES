---
title: Interacciones de configuración entre Grupos de Microsoft 365 y SharePoint
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Más información sobre las interacciones de configuración entre Grupos de Microsoft 365 y SharePoint
ms.openlocfilehash: 2e29132b59b0b63917a87915185cacaacc01bbad
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67727642"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interacciones de configuración entre Grupos de Microsoft 365 y SharePoint

Algunas configuraciones para Grupos de Microsoft 365 y SharePoint en Microsoft 365, especialmente relacionadas con el uso compartido y la creación de grupos y sitios de grupo, se superponen entre sí. En este artículo se proporcionan descripciones de estas interacciones y procedimientos recomendados para trabajar con esta configuración.

![Diagrama de Venn de características de SharePoint, Yammer y grupos.](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Efectos de la configuración de SharePoint en grupos de Microsoft 365

|Configuración de SharePoint|Descripción|Efecto en los grupos de Microsoft 365|Recomendación|
|:-----------------|:----------|:-----------------------------|:-------------|
|Uso compartido externo para la organización y el sitio|Determina si los sitios, archivos y carpetas se pueden compartir con personas ajenas a la organización.|Si la configuración de SharePoint y grupos no coincide, es posible que se bloquee el acceso al sitio a los invitados del grupo o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, compruebe la configuración de grupos y la configuración del sitio de SharePoint para los sitios de grupo conectados a grupos.<br><br>Consulte [Colaborar con invitados en un sitio](./collaborate-in-site.md).|
|Permitir o bloquear dominios|Permite o impide que el contenido se comparta con dominios especificados.|Los grupos no reconocen listas de permitidos ni listas de bloqueo de SharePoint. Los usuarios de dominios no permitidos en SharePoint podrían obtener acceso a SharePoint a través de un grupo.|Administre listas de permitidos de dominio o listas de bloqueo para Azure AD y SharePoint juntos. Cree un proceso de gobernanza en toda la organización para permitir y bloquear dominios.<br><br>Consulte [Configuración de dominio de SharePoint](/sharepoint/restricted-domains-sharing) y [Configuración de dominio de Azure AD](/azure/active-directory/b2b/allow-deny-list)|
|Permitir que solo los usuarios en grupos de seguridad específicos compartan externamente|Especifica grupos de seguridad que pueden compartir sitios, carpetas y archivos externamente.|Esta configuración no afecta a los propietarios de grupos que comparten grupos externamente. Los invitados del grupo tienen acceso al sitio de SharePoint asociado.||
|Configuración de uso compartido de sitios de SharePoint|Determina quién puede compartir el sitio directamente fuera de la pertenencia a grupos. Esto lo configura el propietario del grupo o del sitio.|Esta configuración no afecta directamente al grupo, pero puede permitir que los usuarios se agreguen a un sitio y no tengan acceso a otros recursos del grupo.|Considere la posibilidad de usar esta configuración para limitar el uso compartido del sitio directamente y administrar el acceso al sitio a través del grupo.|
|Permitir a los usuarios crear sitios desde la página de inicio de SharePoint y OneDrive|Especifica si los usuarios pueden crear nuevos sitios de SharePoint.|Si esta configuración está desactivada, los usuarios pueden seguir creando sitios de grupo conectados a grupos mediante la creación de un grupo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Los efectos de la configuración de grupos de Microsoft 365 en SharePoint

|Configuración de grupos de Microsoft 365|Descripción|Efecto en SharePoint|Recomendación|
|:---------------------------|:----------|:-------------------|:-------------|
|Directivas de nomenclatura|Especifica prefijos y sufijos de nombre de grupo, y palabras bloqueadas para la creación de grupos|Las directivas se aplican a los usuarios que crean sitios de grupo conectados a grupos, pero no sitios de comunicación o sitios con otras plantillas.|Cree instrucciones de nomenclatura independientes para los sitios de comunicación si es necesario.|
|Acceso de invitado de grupo|Especifica si se pueden agregar personas ajenas a la organización a grupos.|Si la configuración de SharePoint y grupos no coincide, es posible que se bloquee el acceso al sitio a los invitados del grupo o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, compruebe la configuración de grupos y la configuración del sitio de SharePoint para los sitios de grupo conectados a grupos.<br><br>Consulte [Colaborar con invitados en un sitio](./collaborate-in-site.md)|
|Creación de grupos por grupo de seguridad|Los grupos solo los pueden crear los miembros de un grupo de seguridad específico.|Los usuarios que no sean miembros del grupo de seguridad no podrán crear un sitio de grupo conectado al grupo.|Asegúrese de que el proceso para solicitar un grupo incluye instrucciones para solicitar un sitio.|
|Directiva de expiración de grupo|Especifica un período de tiempo después del cual se eliminarán automáticamente los grupos que no se usan activamente.|Cuando se elimina el grupo, también se elimina el sitio de SharePoint asociado. El contenido protegido por directivas de retención se conserva.|Use directivas de expiración para evitar la expansión de grupos y sitios no utilizados.|

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Colaborar con personas ajenas a la organización](./collaborate-with-people-outside-your-organization.md)

[Administrar la creación de un sitio de SharePoint](/sharepoint/manage-site-creation)