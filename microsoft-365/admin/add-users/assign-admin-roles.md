---
title: Asignar roles de administrador al centro de administración de Microsoft 365
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
description: Obtenga información sobre cómo asignar roles de administrador a un usuario o a varios usuarios de la empresa para que puedan realizar tareas específicas en el centro de administración.
ms.openlocfilehash: cd50faf5db5e674e865e0913cae14a68a202bd1f
ms.sourcegitcommit: 2e9e309ec09e5275ac6b3b425fba48a9ffce8eb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44900781"
---
# <a name="assign-admin-roles"></a>Asignar roles de administrador

Si es la persona que compró su suscripción de empresa de Microsoft, será el administrador global. Esto significa que tiene un control ilimitado sobre los productos de sus suscripciones y puede obtener acceso a la mayoría de los datos.

Para obtener más información, vea [acerca de los roles de administrador](about-admin-roles.md).

Cuando se agregan nuevos usuarios, si no se les asigna un rol de administrador, se encuentran en el *rol de usuario* y no tienen privilegios de administrador en ninguno de los centros de administración de Microsoft. Pero, si necesita ayuda para hacer cosas, puede asignar un rol de administrador a un usuario. Por ejemplo, si necesita que alguien le ayude a restablecer contraseñas, no debería asignarles el rol de administrador global, debe asignarles el rol de administrador de contraseñas. Tener demasiados administradores globales, con acceso ilimitado a sus datos y a la empresa en línea, es un riesgo para la seguridad.

Vea un breve vídeo sobre cómo agregar un administrador.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="assign-admin-roles"></a>Asignar roles de administrador 

::: moniker range="o365-worldwide"

Puede asignar usuarios a un rol de dos maneras distintas:

- Puede ir a los detalles del usuario y **administrar funciones** para asignar una función al usuario.
- O bien, puede ir a **roles** , seleccionar el rol y, a continuación, agregar varios usuarios a él.

### <a name="assign-admin-roles-to-users-using-roles"></a>Asignar roles de administrador a los usuarios mediante roles

1. En el centro de administración, vaya **a roles roles** > **Roles** para ver todos los roles de administrador disponibles para su organización.
2. Seleccione el rol de administrador al que desea asignar el usuario.
3. Seleccione **administradores asignados** > **Add**.
4. Escriba el nombre para **Mostrar** o el nombre para mostrar del usuario y, a **continuación, seleccione**el usuario de la lista de sugerencias.
5. Agregue varios usuarios hasta que haya terminado.
6. Seleccione **Guardar**y, a continuación, el usuario se agregará a la lista de administradores asignados.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Asignar un usuario a un rol de administrador desde usuarios activos

1. En el centro de administración, vaya **a la página usuarios** > [activos](https://go.microsoft.com/fwlink/p/?linkid=834822) .

2. En la página **usuarios activos** , seleccione el usuario cuyo rol de administrador quiera cambiar. En el panel flotante, junto a **roles**, seleccione **administrar roles**.

3. Seleccione el rol de administrador que desea asignar al usuario. Si no ve la función que está buscando, seleccione **Mostrar todo** en la parte inferior de la lista.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. En la página **usuarios activos** , seleccione el usuario cuyo rol de administrador quiera cambiar. En el panel flotante, junto a **roles**, seleccione **Editar**. 

    Si no ve la opción **Editar** , no tiene permiso para editar y no puede asignar roles de administrador a otras personas. Solicite a un administrador global de su empresa que le asigne funciones. En una pequeña empresa, el propietario de la empresa (la persona que compró la suscripción) es un administrador global. En una empresa grande, las personas clave del Departamento de TI son administradores globales.

3. Seleccione **Administrador personalizado** para ver una lista de los roles que ha personalizado para usted. Para obtener una descripción de cada rol, consulte Acerca de los [roles de administrador.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. En la página **usuarios activos** , seleccione el usuario cuyo rol de administrador quiera cambiar. En el panel flotante, junto a **roles**, seleccione **Editar**.

    Si no ve la opción **Editar** , no tiene permiso para editar y no puede asignar roles de administrador a otras personas. Solicite a un administrador global de su empresa que le asigne funciones. En una pequeña empresa, el propietario de la empresa (la persona que compró la suscripción) es un administrador global. En una empresa grande, las personas clave del Departamento de TI son administradores globales.

3. Seleccione **Administrador personalizado** para ver una lista de los roles que ha personalizado para usted. Para obtener una descripción de cada rol, consulte Acerca de los [roles de administrador.](about-admin-roles.md)

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a>Asignar roles de administrador a varios usuarios

Si conoce PowerShell, vea [asignar roles a cuentas de usuario con PowerShell](https://go.microsoft.com/fwlink/?linkid=854257). Es ideal para asignar roles a cientos de usuarios.
  
Use las siguientes instrucciones para asignar roles a decenas de usuarios.

::: moniker range="o365-worldwide"


## <a name="check-your-permissions"></a>Comprobar sus permisos

Es posible que no disponga de los permisos correctos para asignar roles de administrador a otros usuarios. Asegúrese de que tiene los permisos correctos o pida a otro administrador que le asigne roles.

::: moniker-end

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los roles de administración de Microsoft 365](about-admin-roles.md)

[Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[Asignar roles a cuentas de usuario con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[Autorizar o quitar relaciones de asociados](../misc/add-partner.md)