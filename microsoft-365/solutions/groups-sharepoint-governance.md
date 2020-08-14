---
title: Interacciones de configuración entre los grupos de Microsoft 365 y SharePoint
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Obtenga información sobre las interacciones de configuración entre los grupos de Microsoft 365 y SharePoint
ms.openlocfilehash: 0c9fdd69db82985039bae03768aa0c19f514c99f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662836"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interacciones de configuración entre los grupos de Microsoft 365 y SharePoint

Algunas configuraciones para los grupos de Microsoft 365 y SharePoint en Microsoft 365, especialmente relacionadas con el uso compartido y el grupo y la creación de sitios de grupo, se superponen entre sí. En este artículo se proporcionan descripciones de las interacciones y los procedimientos recomendados para trabajar con esta configuración.

![Diagrama de Venn de características de SharePoint, Yammer y grupos](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Efectos de la configuración de SharePoint en grupos de 365 de Microsoft

|Configuración de SharePoint|Descripción|Efecto en los grupos de 365 de Microsoft|Recomendación|
|:-----------------|:----------|:-----------------------------|:-------------|
|Uso compartido externo de la organización y el sitio|Determina si se pueden compartir sitios, archivos y carpetas con personas de fuera de la organización.|Si la configuración de SharePoint y los grupos no coinciden, es posible que los invitados del grupo tengan bloqueado el acceso al sitio o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, Compruebe la configuración de los grupos y de los sitios de SharePoint para los sitios de grupo conectados a un grupo.<br><br>Consulte [colaborar con invitados en un sitio](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site).|
|Permitir/bloquear dominio|Permite o impide que el contenido se comparta con los dominios especificados.|Los grupos no reconocen las listas permitir o bloquear de SharePoint. Los usuarios de los dominios no permitidos en SharePoint podrían obtener acceso a SharePoint a través de un grupo.|Administre las listas de permitidos y bloqueados de dominio conjuntamente para Azure AD y SharePoint. Crear un proceso de gobierno para toda la organización para permitir y bloquear dominios.<br><br>Ver la [configuración de dominio de SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) y la configuración de dominio de [Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Permitir que solo los usuarios de grupos de seguridad específicos compartan externamente|Especifica los grupos de seguridad que pueden compartir los sitios, las carpetas y los archivos de forma externa.|Esta configuración no afecta a los propietarios de grupo que comparten grupos de forma externa. Los invitados del grupo tienen acceso al sitio de SharePoint asociado.||
|Configuración de uso compartido de sitios de SharePoint|Determina quién puede compartir el sitio directamente fuera de la pertenencia a grupos. Esto lo configura el propietario del grupo o del sitio.|Esta configuración no afecta directamente al grupo, pero puede permitir que se agreguen usuarios a un sitio y no tengan acceso a otros recursos de grupo.|Considere la posibilidad de usar esta configuración para limitar el uso compartido del sitio de forma directa y administrar el acceso al sitio a través del grupo.|
|Permitir a los usuarios crear sitios desde la página de inicio de SharePoint y OneDrive|Especifica si los usuarios pueden crear nuevos sitios de SharePoint.|Si esta opción está desactivada, los usuarios pueden crear sitios de grupo conectados a grupos mediante la creación de un grupo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Efectos de la configuración de grupos de 365 de Microsoft en SharePoint

|Configuración de Microsoft 365 Groups|Descripción|Efecto en SharePoint|Recomendación|
|:---------------------------|:----------|:-------------------|:-------------|
|Directivas de nomenclatura|Especifica los prefijos y los sufijos de nombre de grupo, y las palabras bloqueadas para la creación de grupos|Las directivas se aplican a los usuarios que crean sitios de grupo conectados a un grupo, pero no a sitios o sitios de comunicación con otras plantillas.|Cree una guía de nomenclatura separada para los sitios de comunicación si es necesario.|
|Acceso de invitado de grupo|Especifica si las personas de fuera de la organización se pueden agregar a los grupos.|Si la configuración de SharePoint y los grupos no coinciden, es posible que los invitados del grupo tengan bloqueado el acceso al sitio o que el acceso externo esté disponible en el sitio, pero no en el grupo.|Al cambiar la configuración de uso compartido, Compruebe la configuración de los grupos y de los sitios de SharePoint para los sitios de grupo conectados a un grupo.<br><br>Consulte [colaborar con invitados en un sitio](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Creación de grupos por grupo de seguridad|Los grupos solo pueden ser creados por miembros de un grupo de seguridad específico.|Los usuarios que no son miembros del grupo de seguridad no podrán crear un sitio de equipo conectado a un grupo.|Asegúrese de que el proceso para solicitar un grupo incluye instrucciones para solicitar un sitio.|
|Directiva de expiración de grupos|Especifica un período de tiempo tras el cual los grupos que no se usan de forma activa se eliminarán automáticamente.|Cuando se elimina el grupo, también se elimina el sitio de SharePoint asociado. Se conserva el contenido protegido por las directivas de retención.|Use directivas de expiración para evitar la proliferación de grupos y sitios sin usar.|

## <a name="related-topics"></a>Temas relacionados

[Colaborar con personas fuera de la organización](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Administrar la creación de sitios en SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)