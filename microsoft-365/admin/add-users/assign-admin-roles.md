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
ms.localizationpriority: medium
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
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Obtenga información sobre cómo asignar roles de administrador a un usuario o varios usuarios de su empresa para que puedan realizar tareas específicas en el Centro de administración.
ms.openlocfilehash: fd38bb9ed378e6b3ffc20a79ca71eb2943599dcc
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370625"
---
# <a name="assign-admin-roles"></a>Asignar roles de administrador

Si eres la persona que compró tu suscripción a Microsoft Business, eres el administrador global. Esto significa que tienes un control ilimitado sobre los productos de tus suscripciones y puedes acceder a la mayoría de los datos.

Para obtener más información, vea [Sobre los roles de administrador](about-admin-roles.md).

Cuando agregas nuevos usuarios, si no les asignas un  rol de administrador, entonces están en el rol de usuario y no tienen privilegios de administrador en ninguno de los centros de administración de Microsoft. Pero si necesitas ayuda para hacer las cosas, puedes asignar un rol de administrador a un usuario. Por ejemplo, si necesita que alguien le ayude a restablecer las contraseñas, no debe asignarles el rol de administrador global, debe asignarles el rol de administrador de contraseñas. Tener demasiados administradores globales, con acceso ilimitado a sus datos y empresa en línea, es un riesgo de seguridad.

## <a name="watch-add-an-admin"></a>Watch: Add an admin

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

1. Cuando te registras en Microsoft 365 Empresa, automáticamente te conviertes en un administrador global. Para ayudar a administrar la empresa, también puedes hacer administradores de otras personas. 
1. En el Centro de administración de Microsoft 365, seleccione **Usuarios**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Usuarios activos.**</a>.
1. Elija el usuario que desea crear un administrador y, a continuación, seleccione **Administrar roles**.

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="assign-admin-roles"></a>Asignar roles de administrador 

Puede asignar usuarios a un rol de dos maneras diferentes:

- Puede ir a los detalles del usuario y Administrar **roles** para asignar un rol al usuario.
- O bien, puede ir a **Roles** y seleccionar el rol y, a continuación, agregarle varios usuarios.

### <a name="assign-admin-roles-to-users-using-roles"></a>Asignar roles de administrador a usuarios mediante roles

1. En el Centro de administración, vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**Asignaciones de roles**</a>. Elija las **pestañas Azure AD** **o Intune** para ver los roles de administrador disponibles para su organización.
2. Seleccione el rol de administrador al que desea asignar el usuario.
3. Seleccione **Administradores asignados**  >  **Agregar**.
4. Escriba el nombre para  **mostrar** o el nombre de usuario del usuario y, a continuación, seleccione el usuario en la lista de sugerencias.
5. Agregue varios usuarios hasta que haya terminado.
6. Seleccione **Guardar** y, a continuación, el usuario se agregará a la lista de administradores asignados.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Asignar un usuario a un rol de administrador desde Usuarios activos

::: moniker range="o365-worldwide"

1. En el Centro de administración, vaya a **La página Usuarios** usuarios > [activos.](https://go.microsoft.com/fwlink/p/?linkid=834822)

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. En la **página Usuarios activos,** seleccione el usuario cuyo rol de administrador desea cambiar. En el panel desplegable, en **Roles,** seleccione **Administrar roles**.

3. Seleccione el rol de administrador que quiere asignar al usuario. Si no ve el rol que está buscando, seleccione **Mostrar todo** en la parte inferior de la lista.

## <a name="assign-admin-roles-to-multiple-users"></a>Asignar roles de administrador a varios usuarios

Si conoce PowerShell, vea [Asignar roles a cuentas de usuario con PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md). Es ideal para asignar roles a cientos de usuarios.
  
Use las siguientes instrucciones para asignar roles a decenas de usuarios.

## <a name="check-admin-roles-in-your-organization"></a>Comprobar roles de administrador en la organización

Es posible que no tenga los permisos correctos para asignar roles de administrador a otros usuarios. Compruebe que tiene los permisos correctos o pida a otro administrador que le asigne roles.

Puede comprobar los permisos de roles de administración de dos maneras diferentes:

- Puede ir a los detalles del usuario y buscar en **Roles** en la **página** Cuenta.
- O bien, puede ir a **Roles** y seleccionar el rol de administrador y seleccionar administradores asignados para ver qué usuarios están asignados.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los roles de administrador en Microsoft 365](about-admin-roles.md) (artículo)\
[Azure AD roles integrados](/azure/active-directory/roles/permissions-reference) (artículo)\
[Asignar roles a cuentas de usuario con PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (artículo)\
[Autorizar o quitar relaciones de partner](../misc/add-partner.md) (artículo)