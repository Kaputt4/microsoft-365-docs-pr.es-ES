---
title: Asignar roles de administrador al Centro de administración de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
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
description: Obtenga información sobre cómo asignar roles de administrador a un usuario o a varios usuarios de su empresa para que puedan realizar tareas específicas en el centro de administración.
ms.openlocfilehash: 8b039d1ae1408a50dc1307e831f702576896427c
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195971"
---
# <a name="assign-admin-roles-in-the-microsoft-365-admin-center"></a>Asignar roles de administrador en el Centro de administración de Microsoft 365

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

Si es la persona que compró su suscripción empresarial de Microsoft, es el administrador global. Esto significa que tiene control ilimitado sobre los productos de sus suscripciones y puede acceder a la mayoría de los datos.

Para más información, consulte[Sobre los roles de administrador](about-admin-roles.md).

Al agregar nuevos usuarios, si no les asigna un rol de administrador, se encuentran en el *rol de usuario* y no tienen privilegios de administrador en ninguno de los centros de administración de Microsoft. Pero si necesita ayuda para hacer las cosas, puede asignar un rol de administrador a un usuario. Por ejemplo, si necesita que alguien le ayude a restablecer las contraseñas, no debe asignarle el rol de administrador global, debe asignarle el rol de administrador de contraseñas. Tener demasiados administradores globales, con acceso ilimitado a sus datos y empresa en línea, es un riesgo de seguridad.

## <a name="watch-add-an-admin"></a>Inspección: Agregar un administrador

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198030).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

1. Al registrarse en Microsoft 365 Empresa, se convierte automáticamente en administrador global. Para ayudar a administrar la empresa, también puede hacer administradores a otras personas. 
1. En el Centro de administración de Microsoft 365, seleccione **Usuarios**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Usuarios activos.**</a>.
1. Elija el usuario que desea convertir en administrador y, a continuación, seleccione **Administrar roles**.

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="assign-admin-roles"></a>Asignar roles de administrador 

Puede asignar usuarios a un rol de dos maneras diferentes:

- Puede ir a los detalles del usuario y **Administrar roles** para asignar un rol al usuario.
- O bien, puede ir a **Roles** , seleccionar el rol y agregarle varios usuarios.

### <a name="assign-admin-roles-to-users-using-roles"></a>Asignación de roles de administrador a usuarios mediante roles

1. En el centro de administración, vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**Asignaciones de roles**</a>. Elija las pestañas **Azure AD** o **Intune** para ver los roles de administrador disponibles para su organización.
2. Seleccione el rol de administrador al que desea asignar al usuario.
3. Seleccione **Administradores asignados** > **Agregar**.
4. Escriba el **nombre para mostrar** o el **nombre de usuario** del usuario y, a continuación, seleccione el usuario en la lista de sugerencias.
5. Agregue varios usuarios hasta que haya terminado.
6. Seleccione **Guardar** y, a continuación, el usuario se agregará a la lista de administradores asignados.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Asignar un usuario a un rol de administrador desde Usuarios activos

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** > [activos](https://go.microsoft.com/fwlink/p/?linkid=834822) .

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. En la página **Usuarios activos**, seleccione el usuario cuyo rol de administrador desea cambiar. En el panel desplegable, en **Roles**, seleccione **Administrar roles**.

3. Seleccione el rol de administrador que quiere asignar al usuario. Si no ve el rol que está buscando, seleccione **Mostrar todo** en la parte inferior de la lista.

## <a name="assign-admin-roles-to-multiple-users"></a>Asignar roles de administrador a varios usuarios

Si conoce PowerShell, consulte [Asignación de roles a cuentas de usuario con PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md). Es ideal para asignar roles a cientos de usuarios.
  
Use las siguientes instrucciones para asignar roles a decenas de usuarios.

## <a name="check-admin-roles-in-your-organization"></a>Comprobación de roles de administrador en la organización

Es posible que no tenga los permisos correctos para asignar roles de administrador a otros usuarios. Compruebe que tiene los permisos correctos o pida a otro administrador que le asigne roles.

Puede comprobar los permisos de rol de administrador de dos maneras diferentes:

- Puede ir a los detalles del usuario y buscar en **Roles** en la página **Cuenta** .
- O bien, puede ir a **Roles** y seleccionar el rol de administrador y seleccionar administradores asignados para ver qué usuarios están asignados.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los roles de administrador en Microsoft 365](about-admin-roles.md) (artículo)\
[Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference) (artículo)\
[Asignación de roles a cuentas de usuario con PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (artículo)\
[Autorización o eliminación de relaciones con asociados](../misc/add-partner.md) (artículo)