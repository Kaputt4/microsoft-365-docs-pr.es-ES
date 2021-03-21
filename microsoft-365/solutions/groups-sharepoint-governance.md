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
description: Información sobre las interacciones de configuración entre grupos de Microsoft 365 y SharePoint
ms.openlocfilehash: e1aeaca792fb551de503bd4c68256ccf14f45022
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921041"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interacciones de configuración entre grupos de Microsoft 365 y SharePoint

Algunas opciones de configuración de Grupos de Microsoft 365 y SharePoint en Microsoft 365, especialmente relacionadas con el uso compartido y la creación de sitios de grupo y grupo, se superponen entre sí. En este artículo se proporcionan descripciones de estas interacciones y procedimientos recomendados para trabajar con esta configuración.

![Diagrama venn de características de SharePoint, Yammer y grupos](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Efectos de la configuración de SharePoint en grupos de Microsoft 365

|Configuración de SharePoint|Descripción|Efecto en grupos de Microsoft 365|Recomendación|
|:-----------------|:----------|:-----------------------------|:-------------|
|Uso compartido externo para la organización y el sitio|Determina si los sitios, archivos y carpetas se pueden compartir con personas ajenas a la organización.|Si la configuración de SharePoint y grupos no coincide, es posible que los invitados del grupo no tengan acceso al sitio o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, compruebe la configuración de grupos y la configuración del sitio de SharePoint para los sitios de grupo conectados a grupos.<br><br>Consulte [Colaborar con invitados en un sitio](./collaborate-in-site.md).|
|Domain allow/block|Permite o impide que el contenido se comparta con dominios especificados.|Los grupos no reconocen listas de permitidos o bloqueados de SharePoint. Los usuarios de dominios no permitidos en SharePoint podrían obtener acceso a SharePoint a través de un grupo.|Administrar listas de dominios permitidos y bloqueados para Azure AD y SharePoint juntos. Cree un proceso de gobierno en toda la organización para permitir y bloquear dominios.<br><br>Consulte [Configuración de dominio de SharePoint](/sharepoint/restricted-domains-sharing) y Configuración de dominio de Azure [AD](/azure/active-directory/b2b/allow-deny-list)|
|Permitir que solo los usuarios en grupos de seguridad específicos compartan externamente|Especifica grupos de seguridad que pueden compartir sitios, carpetas y archivos externamente.|Esta configuración no afecta a los propietarios de grupos que comparten grupos externamente. Los invitados de grupo tienen acceso al sitio de SharePoint asociado.||
|Configuración de uso compartido de sitios de SharePoint|Determina quién puede compartir el sitio directamente fuera de la pertenencia a grupos. El propietario del sitio o grupo lo configura.|Esta configuración no afecta directamente al grupo, pero puede permitir a los usuarios agregarse a un sitio y no tener acceso a otros recursos de grupo|Considere la posibilidad de usar esta configuración para limitar el uso compartido del sitio directamente y administrar el acceso al sitio a través del grupo.|
|Permitir a los usuarios crear sitios desde la página de inicio de SharePoint y OneDrive|Especifica si los usuarios pueden crear nuevos sitios de SharePoint.|Si esta configuración está desactivada, los usuarios aún pueden crear sitios de grupo conectados a grupos mediante la creación de un grupo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Efectos de la configuración de grupos de Microsoft 365 en SharePoint

|Configuración de grupos de Microsoft 365|Descripción|Efecto en SharePoint|Recomendación|
|:---------------------------|:----------|:-------------------|:-------------|
|Directivas de nomenclatura|Especifica prefijos y sufijos de nombre de grupo y palabras bloqueadas para la creación de grupos|Las directivas se aplican para los usuarios que crean sitios de grupo conectados a grupos, pero no sitios de comunicación o sitios con otras plantillas.|Cree instrucciones de nomenclatura independientes para los sitios de comunicación si es necesario.|
|Acceso de invitado de grupo|Especifica si se pueden agregar personas fuera de la organización a grupos.|Si la configuración de SharePoint y grupos no coincide, es posible que los invitados del grupo no tengan acceso al sitio o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, compruebe la configuración de grupos y la configuración del sitio de SharePoint para los sitios de grupo conectados a grupos.<br><br>Consulta [Colaborar con invitados en un sitio](./collaborate-in-site.md)|
|Creación de grupos por grupo de seguridad|Los grupos solo los pueden crear los miembros de un grupo de seguridad específico.|Los usuarios que no sean miembros del grupo de seguridad no podrán crear un sitio de grupo conectado a un grupo.|Asegúrese de que el proceso para solicitar un grupo incluye instrucciones para solicitar un sitio.|
|Directiva de expiración de grupo|Especifica un período de tiempo después del cual los grupos que no se usan activamente se eliminarán automáticamente.|Cuando se elimina el grupo, también se elimina el sitio de SharePoint asociado. El contenido protegido por directivas de retención se conserva.|Use directivas de expiración para evitar la expansión de sitios y grupos no usados.|

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Colaborar con personas ajenas a la organización](./collaborate-with-people-outside-your-organization.md)

[Administrar la creación de un sitio de SharePoint](/sharepoint/manage-site-creation)