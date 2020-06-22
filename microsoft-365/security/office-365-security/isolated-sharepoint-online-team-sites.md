---
title: Sitios de grupo de SharePoint Online aislados
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Obtenga información sobre los sitios de grupo aislados de SharePoint Online incluidos usos, requisitos y características con los que se pueden usar.
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819538"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Sitios de grupo de SharePoint Online aislados

 **Resumen:** obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.
  
SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.
  
However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:
  
- Un proyecto secreto en su organización.
    
- La ubicación de propiedad intelectual altamente confidencial o valiosa para su organización.
    
- Los recursos de una acción legal realizada por su organización o por la organización que sea objeto de esa acción legal.
    
- Para compartir una suscripción de Microsoft 365 entre varias organizaciones que se superpongan parcialmente, pero que, en su mayoría, existan como entidades empresariales separadas.
    
Estos son los requisitos para un sitio aislado:
  
- Solo los administradores de SharePoint Online pueden administrar el sitio, como la pertenencia a grupos para el acceso al sitio y la configuración de permisos personalizados.
    
- Los miembros del sitio no pueden invitar a otros miembros al sitio de grupo.
    
- Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.
    
The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.
  
Un sitio aislado se puede usar con otras características, como:
  
- Information Rights Management, para garantizar que los recursos del sitio permanezcan cifrados, incluso si se descargan localmente y se cargan en otro sitio que esté disponible para toda la organización.
    
- Prevención de pérdida de datos para impedir que los usuarios envíen los recursos del sitio, como archivos, por correo electrónico.
    
## <a name="next-steps"></a>Pasos siguientes

Para probar un sitio de grupo de SharePoint Online aislado en una suscripción de prueba, vea las instrucciones paso a paso en [Entorno de desarrollo y pruebas en un sitio de grupo aislado de SharePoint Online](isolated-sharepoint-online-team-site-dev-test-environment.md).
  
Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="related-topics"></a>Temas relacionados

[Diseñar un sitio de grupo de SharePoint Online aislado](design-an-isolated-sharepoint-online-team-site.md)
  
[Administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)


