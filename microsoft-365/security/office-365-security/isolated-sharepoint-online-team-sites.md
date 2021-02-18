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
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Obtenga información sobre los sitios de grupo aislados de SharePoint Online incluidos usos, requisitos y características con los que se pueden usar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286590"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Sitios de grupo de SharePoint Online aislados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 de Microsoft Defender para Office 365](office-365-atp.md)
- SharePoint Online 

 **Resumen:** obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.

Los sitios de grupo de SharePoint Online son una forma sencilla de crear rápidamente un espacio para la colaboración. Los usuarios pueden colaborar en notas, documentos, artículos, calendarios y otros recursos en Microsoft Office 365. Los sitios de grupo de SharePoint Online se basan en un grupo de Microsoft 365 y tienen un modelo de administración simplificado para permitir la colaboración abierta con un conjunto privado de miembros del grupo o con toda la organización. Un sitio de grupo predeterminado de SharePoint Online permite a los miembros del grupo de Microsoft 365 invitar a otros usuarios y controlar la configuración de los permisos.

Sin embargo, en ocasiones necesitará que el acceso al sitio esté controlado por pertenencias a grupos y que los niveles de permiso de SharePoint Online sean gestionados por administradores de SharePoint. Esto se llama sitio aislado, y es aislado al conjunto de usuarios que colaboran, ven los contenidos o administran el sitio. Puede que necesite un sitio aislado por los siguientes motivos:

- Un proyecto secreto en su organización.

- La ubicación de propiedad intelectual altamente confidencial o valiosa para su organización.

- Los recursos de una acción legal realizada por su organización o por la organización que sea objeto de esa acción legal.

- Para compartir una suscripción de Microsoft 365 entre varias organizaciones que se superpongan parcialmente, pero que, en su mayoría, existan como entidades empresariales separadas.

Estos son los requisitos para un sitio aislado:

- Solo los administradores de SharePoint Online pueden administrar el sitio, como la pertenencia a grupos para el acceso al sitio y la configuración de permisos personalizados.

- Los miembros del sitio no pueden invitar a otros miembros al sitio de grupo.

- Los usuarios que no sean miembros del sitio aislado no pueden solicitar acceso al sitio. Recibirán una página web de acceso denegado cuando intenten obtener acceso a cualquier dirección URL asociada con el sitio.

La ventaja de exigir un control de acceso centralizado y permisos personalizados por los administradores de SharePoint Online es que el sitio permanecerá aislado con el paso del tiempo. Por ejemplo, los miembros actuales no pueden, ya sea de forma intencionada o por error, invitar o configurar permisos personalizados para otros usuarios de la suscripción de Microsoft 365 que no tendrían que ser miembros del sitio.

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
