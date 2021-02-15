---
title: Agregar o quitar miembros de grupos de Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Obtenga información sobre cómo agregar un miembro a un grupo, quitar miembro del grupo y administrar el estado del propietario del grupo en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 34c026bced5563e07a1ae0d13f4c691cfaf3f624
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663248"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Agregar o quitar miembros de grupos de Microsoft 365 mediante el Centro de administración

En Microsoft 365, los miembros del grupo suelen crear sus propios grupos, agregarse a sí mismos a los grupos a los que desean unirse o son invitados por los propietarios del grupo. Si cambia la propiedad del grupo o si determina que un miembro debe agregarse o quitarse, como administrador también puede realizar ese cambio. Solo un administrador global, un administrador de Exchange, un administrador de grupos o un administrador de usuarios pueden realizar estos cambios. [¿Qué es un grupo de Microsoft 365?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Si no es administrador, puede agregar o [quitar miembros con Outlook.](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Agregar un miembro a un grupo en el centro de administración

1. En el centro de administración, vaya a la [**página Grupos activos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Haga clic en el nombre de un grupo.

3. En el panel de detalles, en **la** pestaña Miembros, seleccione Ver todos y **administrar** miembros y, a continuación, seleccione **Agregar miembros.**

4. Busque o seleccione el nombre del miembro que desee agregar.

5. Seleccione **Guardar**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Agregar un grupo a un miembro en el centro de administración

1. En el centro de administración, vaya a la [**página Usuarios activos.**](https://admin.microsoft.com/Adminportal/Home?#/users)  

2. Haga clic en un usuario.

3. En el panel de detalles, en la **pestaña** Cuenta, seleccione **Administrar grupos.**

4. Busque o seleccione el nombre del grupo que desea agregar.

5. Seleccione **Guardar**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Quitar un miembro de un grupo en el centro de administración

> [!NOTE]
> Cuando quitas un miembro de un grupo privado, la persona tarda 5 minutos en bloquearse del grupo.

1. En el centro de administración, vaya a la [**página Grupos activos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Haga clic en el nombre de un grupo.

3. En el panel de detalles, en la **pestaña Miembros,** seleccione **Ver todos y administrar miembros.**

4. Junto al miembro que desea quitar, seleccione la X.

5. Seleccione **Guardar para** quitar el miembro.

## <a name="manage-group-owner-status"></a>Administrar el estado del propietario del grupo

De manera predeterminada, la persona que creó el grupo es el propietario del grupo. A menudo, un grupo tendrá varios propietarios con fines de compatibilidad con las copias de seguridad o por otras razones. Los miembros pueden promoverse al estado de propietario y los propietarios pueden degradarse al estado de miembro.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Promover un miembro al estado de propietario en el centro de administración

1. En el centro de administración, vaya a la [**página Grupos activos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Haga clic en el nombre de un grupo.

3. En el panel de detalles, en la pestaña **Miembros,** seleccione **Ver todos y administrar propietarios.**

4. Seleccione **Agregar propietarios.**

5. Active la casilla situada junto al nombre del miembro que desea agregar.

6. Seleccione **Guardar** y, a continuación, **Cerrar**.

### <a name="remove-owner-status-in-the-admin-center"></a>Quitar el estado del propietario en el centro de administración

1. En el centro de administración, vaya a la [**página Grupos activos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Haga clic en el nombre de un grupo.

3. En el panel de detalles, en la **pestaña Miembros,** seleccione **Ver todos y administrar propietarios.**

4. Seleccione la X junto al nombre del propietario.

5. Seleccione **Guardar**.

## <a name="more-on-managing-membership"></a>Más información sobre cómo administrar la pertenencia

- [Administrar grupos dinámicamente en Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=847632): vea la sección "¿Cómo puedo administrar la pertenencia a un grupo dinámicamente?"

- Para agregar cientos o miles de usuarios a grupos, use [add-UnifiedGroupLinks](https://docs.microsoft.com/powershell/module/exchange/add-unifiedgrouplinks).

- [Asignar un nuevo propietario a un grupo huérfano](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>Artículos sobre la administración de grupos

- [Actualizar listas de distribución a grupos de Microsoft 365 en Outlook](../manage/upgrade-distribution-lists.md)

- [Por qué debería actualizar sus listas de distribución a grupos de Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [Administrar el acceso de invitado en grupos de Microsoft 365](manage-guest-access-in-groups.md)

- [Administrar grupos de Microsoft 365 con PowerShell:](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)en este artículo se presentan los cmdlets clave y se proporcionan ejemplos

- [Directiva de nomenclatura de grupos de Microsoft 365](groups-naming-policy.md)
