---
title: Diseñar un sitio de grupo de SharePoint Online aislado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Diseñe sitios de grupo aislados de SharePoint Online, incluidos los niveles de permisos, asigne permisos a usuarios con grupos de acceso y grupos anidados de Azure AD.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165516"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Diseñar un sitio de grupo de SharePoint Online aislado

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


 **Resumen:** Paso a paso por el proceso de diseño para sitios de grupo aislados de SharePoint Online.

Este artículo le lleva a través de las decisiones de diseño clave que debe tomar antes de crear un sitio de grupo de SharePoint Online aislado.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: Determinar los grupos y niveles de permisos de SharePoint

Todos los sitios de grupo de SharePoint Online se crean de forma predeterminada con los siguientes grupos de SharePoint:

- \<site name> Miembros

- \<site name> Visitantes

- \<site name> Propietarios

Estos grupos son independientes de los grupos de Microsoft 365 y Azure Active Directory (AD) y son la base para asignar permisos para los recursos del sitio.

El conjunto de permisos específicos que determina lo que un miembro de un grupo de SharePoint puede hacer en un sitio es un nivel de permisos. Hay tres niveles de permisos de forma predeterminada para un sitio de grupo de SharePoint Online: Edición, Lectura y Control total. En la tabla siguiente se muestra la correlación predeterminada de los grupos de SharePoint y los niveles de permisos asignados:

****

|Grupo de SharePoint|Nivel de permisos|
|---|---|
|\<site name> Miembros|Editar|
|\<site name> Visitantes|Lectura|
|\<site name> Propietarios|Control total|
|

 **Procedimiento recomendado:** Puede crear grupos y niveles de permisos de SharePoint adicionales. Sin embargo, se recomienda usar los grupos y niveles de permisos predeterminados de SharePoint para el sitio aislado de SharePoint Online.

Estos son los grupos y niveles de permisos predeterminados de SharePoint.

![Los grupos y niveles de permisos predeterminados de SharePoint para un sitio de SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: Asignar permisos a usuarios con grupos de acceso

Puede asignar permisos a los usuarios agregando su cuenta de usuario, o un grupo de Microsoft 365 o Azure AD del que la cuenta de usuario es miembro, a los grupos de SharePoint. Una vez agregadas, a las cuentas de usuario, ya sea directa o indirectamente a través de la pertenencia a un grupo de Microsoft 365 o Azure AD, se les asigna el nivel de permisos asociado con el grupo de SharePoint.

Usar los grupos de SharePoint predeterminados como ejemplo:

- A los miembros del **\<site name> grupo de** SharePoint Miembros, que pueden incluir cuentas de usuario y grupos, se les asigna el **nivel de** permiso Editar

- A los miembros del **\<site name> grupo de** Visitantes de SharePoint, que pueden incluir cuentas de usuario y grupos, se les asigna el nivel **de** permisos de lectura

- A los miembros del **\<site name> grupo propietarios** de SharePoint, que pueden incluir tanto cuentas de usuario como grupos, se les asigna el nivel de **permiso Control** total

 **Procedimiento recomendado:** Aunque puede administrar permisos a través de cuentas de usuario individuales, le recomendamos que use un único grupo de Azure AD, conocido como grupo de acceso, en su lugar. Esto simplifica la administración de permisos mediante la pertenencia al grupo de acceso, en lugar de administrar la lista de cuentas de usuario para cada grupo de SharePoint.

Los grupos de Azure AD para Microsoft 365 son diferentes, por ejemplo, grupos de Microsoft 365. Los grupos de Azure AD aparecen en el  Centro  de administración de Microsoft 365 con su tipo establecido en Seguridad y no tienen una dirección de correo electrónico. Los grupos de Azure AD se pueden administrar en:

- Servicios de dominio de Active Directory (AD DS)

    Se trata de grupos que se han creado en la infraestructura local de AD DS y se han sincronizado con su suscripción a Microsoft 365. En el Centro de administración de Microsoft  365, estos grupos tienen un estado **de sincronización con Active Directory.**

- Office 365

    Se trata de grupos que se han creado con el Centro de administración de Microsoft 365, Azure Portal o PowerShell de Microsoft. En el Centro de administración de Microsoft 365, estos grupos tienen un **estado** de **nube.**

 **Procedimiento recomendado:** Si usa AD DS local y se sincroniza con su suscripción de Microsoft 365, realice la administración de usuarios y grupos con AD DS.

Para los sitios de grupo de SharePoint Online aislados, la estructura de grupo recomendada tiene este aspecto:

****

|Grupo de SharePoint|Grupo de acceso basado en Azure AD|Nivel de permisos|
|---|---|---|
|\<site name> Miembros|\<site name> Miembros|Editar|
|\<site name> Visitantes|\<site name> Visores|Lectura|
|\<site name> Propietarios|\<site name> Administradores|Control total|
|

 **Procedimiento recomendado:** Aunque puede usar grupos de Microsoft 365 o Azure AD como miembros de grupos de SharePoint, se recomienda usar grupos de Azure AD. Los grupos de Azure AD, administrados a través de AD DS o Microsoft 365, ofrecen más flexibilidad para usar grupos anidados para asignar permisos.

Estos son los grupos de SharePoint predeterminados configurados para usar grupos de acceso basados en Azure AD.

![Usar grupos de acceso como miembros de grupos de sitios predeterminados de SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

Al diseñar los tres grupos de acceso, tenga en cuenta lo siguiente:

- Solo debe haber unos pocos **\<site name>** miembros en el grupo de acceso Administradores, correspondiente a un pequeño número de administradores de SharePoint Online que administran el sitio de grupo.

- La mayoría de los miembros del sitio están en los grupos **\<site name> de** acceso Miembros o Visores. **\<site name>** Dado que los miembros del **sitio \<site name>** del grupo de acceso Miembros tienen la capacidad de eliminar o modificar recursos del sitio, considere detenidamente su pertenencia. Cuando haya dudas, agregue el miembro del sitio al grupo **\<site name> de acceso** Visores.

Este es un ejemplo de los grupos de SharePoint y grupos de acceso para un sitio aislado denominado ProjectX.

![Ejemplo de uso de grupos de acceso para un sitio de SharePoint Online denominado ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: Usar grupos anidados de Azure AD

Para un proyecto limitado a un número reducido de personas, la mayoría de los escenarios se ajustarán a la mayoría de los escenarios con un solo nivel de grupos de acceso basados en Azure AD agregados a los grupos de SharePoint del sitio. Sin embargo, si tiene un gran número de personas y esas personas ya son miembros de grupos de Azure AD establecidos, puede asignar más fácilmente permisos de SharePoint mediante grupos anidados o grupos que contienen otros grupos como miembros.

Por ejemplo, desea crear un sitio de grupo aislado de SharePoint Online para la colaboración entre los ejecutivos de los departamentos de ventas, marketing, ingeniería, legal y soporte técnico, y esos departamentos ya tienen sus propios grupos con la pertenencia a cuentas de usuario ejecutivo. En lugar de crear un nuevo grupo para los nuevos miembros del sitio y colocar todas las cuentas de usuario ejecutivo individuales en él, coloque los grupos ejecutivos existentes para cada departamento en el nuevo grupo.

 Si comparte una suscripción de Microsoft 365 entre varias organizaciones, es posible que sea difícil administrar un solo nivel de pertenencia a grupos para un sitio aislado de una organización debido al gran número de cuentas de usuario. En este caso, puede usar grupos anidados de Azure AD para cada organización que contenga los grupos dentro de sus organizaciones para administrar los permisos.

Para usar grupos anidados de Azure AD:

1. Identifique o cree los grupos de Azure AD que contendrán cuentas de usuario y agregue las cuentas de usuario apropiadas como miembros.

2. Cree el grupo de acceso basado en Azure AD contenedor que contendrá los demás grupos de Azure AD y agregue esos grupos como miembros.

3. Para el nivel de acceso adecuado para el grupo de acceso de contenedor, identifique el grupo de SharePoint y el nivel de permisos correspondiente.

> [!NOTE]
> No puede usar grupos anidados de Microsoft 365.

Este es un ejemplo de grupos anidados de Azure AD para el grupo de acceso de miembros de ProjectX.

![Ejemplo de uso de grupos de acceso anidados para el grupo de acceso de miembros para el sitio ProjectX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

Dado que todas las cuentas de usuario de los equipos de investigación, ingeniería y proyectos principales están pensadas para ser miembros del sitio, es más fácil agregar sus grupos de Azure AD al grupo de acceso de miembros de ProjectX.

## <a name="next-step"></a>Paso siguiente

Cuando esté listo para crear y configurar un sitio aislado en producción, vea Implementar un sitio de grupo de [SharePoint Online aislado.](deploy-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>Vea también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)

[Administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)
