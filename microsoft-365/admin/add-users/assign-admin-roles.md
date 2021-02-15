---
title: Asignar roles de administrador al Centro de administración de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Obtenga información sobre cómo asignar roles de administrador a un usuario o a varios usuarios de su empresa para que puedan realizar tareas específicas en el centro de administración.
ms.openlocfilehash: c0dfef0860e5729a135a142383bdb60aa9d310be
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906256"
---
# <a name="assign-admin-roles"></a>Asignar roles de administrador

Si es la persona que compró su suscripción empresarial de Microsoft, usted es el administrador global. Esto significa que tienes control ilimitado sobre los productos de tus suscripciones y puedes acceder a la mayoría de los datos.

Para obtener más información, vea [Sobre los roles de administrador](about-admin-roles.md).

Al agregar nuevos usuarios, si no les asigna un rol  de administrador, entonces están en el rol de usuario y no tienen privilegios de administrador en ninguno de los centros de administración de Microsoft. Pero si necesita ayuda para realizar las cosas, puede asignar un rol de administrador a un usuario. Por ejemplo, si necesita que alguien le ayude a restablecer contraseñas, no debe asignarles el rol de administrador global, debe asignarles el rol de administrador de contraseñas. Tener demasiados administradores globales, con acceso ilimitado a los datos y a la empresa en línea, es un riesgo para la seguridad.

## <a name="watch-add-an-adminbrbr"></a>Vea: Agregar un administrador.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="assign-admin-roles"></a>Asignar roles de administrador 

::: moniker range="o365-worldwide"

Puede asignar usuarios a un rol de dos maneras diferentes:

- Puede ir a los detalles del usuario y administrar **roles** para asignar un rol al usuario.
- O bien, puede ir **a Roles,** seleccionar el rol y, a continuación, agregarle varios usuarios.

### <a name="assign-admin-roles-to-users-using-roles"></a>Asignar roles de administrador a usuarios que usan roles

1. En el centro de administración, vaya **a Roles** Roles para ver todos los roles de administrador disponibles para su >  organización.
2. Seleccione el rol de administrador al que desea asignar el usuario.
3. Seleccione **Agregar administradores** > **asignados.**
4. Escriba el nombre para  **mostrar** o el nombre de usuario del usuario y, a continuación, selecciónelo en la lista de sugerencias.
5. Agregue varios usuarios hasta que haya terminado.
6. Seleccione **Guardar** y, a continuación, el usuario se agregará a la lista de administradores asignados.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Asignar un usuario a un rol de administrador de usuarios activos

1. En el centro de administración, vaya a la **página Usuarios** > [activos.](https://go.microsoft.com/fwlink/p/?linkid=834822)

2. En la **página Usuarios activos,** seleccione el usuario cuyo rol de administrador desea cambiar. En el panel desplegable, junto **a Roles,** seleccione **Administrar roles.**

3. Seleccione el rol de administrador que desea asignar al usuario. Si no ve el rol que busca, seleccione **Mostrar todo** en la parte inferior de la lista.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. En la **página Usuarios activos,** seleccione el usuario cuyo rol de administrador desea cambiar. En el panel desplegable, junto a **Roles,** seleccione **Editar**. 

    Si no ve la  opción Editar, no tiene permiso para editar y no puede asignar roles de administrador a otras personas. Pida a un administrador global de su empresa que le asigne roles. En una pequeña empresa, el propietario de la empresa (la persona que compró la suscripción) es un administrador global. En una empresa grande, las personas clave del departamento de TI son administradores globales.

3. Seleccione **Administrador personalizado** para ver una lista de los roles que hemos personalizado. Para obtener una descripción de cada rol, vea [Acerca de los roles de administrador.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. En la **página Usuarios activos,** seleccione el usuario cuyo rol de administrador desea cambiar. En el panel desplegable, junto a **Roles,** seleccione **Editar**.

    Si no ve la  opción Editar, no tiene permiso para editar y no puede asignar roles de administrador a otras personas. Pida a un administrador global de su empresa que le asigne roles. En una pequeña empresa, el propietario de la empresa (la persona que compró la suscripción) es un administrador global. En una empresa grande, las personas clave del departamento de TI son administradores globales.

3. Seleccione **Administrador personalizado** para ver una lista de los roles que hemos personalizado. Para obtener una descripción de cada rol, vea [Acerca de los roles de administrador.](about-admin-roles.md)

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a>Asignar roles de administrador a varios usuarios

Si conoce PowerShell, vea [Asignar roles a cuentas de usuario con PowerShell.](https://go.microsoft.com/fwlink/?linkid=854257) Es ideal para asignar roles a cientos de usuarios.
  
Use las siguientes instrucciones para asignar roles a decenas de usuarios.

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a>Comprobar los roles de administrador de la organización

Es posible que no tenga los permisos correctos para asignar roles de administrador a otros usuarios. Compruebe que tiene los permisos correctos o pida a otro administrador que le asigne roles.

Puede comprobar los permisos de rol de administrador de dos maneras diferentes:

- Puede ir a los detalles del usuario y buscar en **Roles** en la **página Cuenta.**
- O bien, puede ir a **Roles,** seleccionar el rol de administrador y seleccionar los administradores asignados para ver qué usuarios están asignados.

::: moniker-end

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los roles de administración de Microsoft 365](about-admin-roles.md)

[Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[Asignar roles a cuentas de usuario con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell)

[Autorizar o quitar relaciones de asociados](../misc/add-partner.md)