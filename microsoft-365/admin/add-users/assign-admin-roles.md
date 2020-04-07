---
title: Asignar roles de administrador al centro de administración de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: get-started-article
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Obtenga información sobre cómo asignar roles de administrador a un usuario o a varios usuarios de la empresa para que puedan realizar tareas específicas en el centro de administración.
ms.openlocfilehash: 9c10ef7d6dade3d826c9c291e58b3e8e2a58f2a6
ms.sourcegitcommit: 311bbd6f168225ede166d29696126a1e003eee0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "43151388"
---
# <a name="assign-admin-roles"></a>Asignar roles de administrador

Si es la persona que compró su suscripción de empresa de Microsoft, será el administrador global. Esto significa que tiene un control ilimitado sobre los productos de sus suscripciones y puede obtener acceso a la mayoría de los datos.

Para obtener más información, vea [acerca de los roles de administrador](about-admin-roles.md).

Cuando se agregan nuevos usuarios, si no se les asigna un rol de administrador, se encuentran en el *rol de usuario* y no tienen privilegios de administrador en ninguno de los centros de administración de Microsoft. Pero, si necesita ayuda para hacer cosas, puede asignar un rol de administrador a un usuario. Por ejemplo, si necesita que alguien le ayude a restablecer contraseñas, no debería asignarles el rol de administrador global, debe asignarles el rol de administrador de contraseñas. Tener demasiados administradores globales, con acceso ilimitado a sus datos y a la empresa en línea, es un riesgo para la seguridad.

Vea un breve vídeo sobre cómo agregar un administrador.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

::: moniker-end

## <a name="assign-admin-roles"></a>Asignar roles de administrador 

::: moniker range="o365-worldwide"

Puede asignar usuarios a un rol de dos maneras distintas:

- Puede ir a los detalles del usuario y **administrar funciones** para asignar una función al usuario.
- O bien, puede ir a **roles** , seleccionar el rol y, a continuación, agregar varios usuarios a él.

### <a name="assign-admin-roles-to-users-using-roles"></a>Asignar roles de administrador a los usuarios mediante roles

1. En el centro de administración, > vaya **a roles roles para** Ver todos **los roles de** administrador disponibles para su organización.
2. Seleccione el rol de administrador al que desea asignar el usuario.
3. > **Add**Seleccione **administradores asignados** .
4. Escriba el nombre para **Mostrar** o el nombre para mostrar del usuario y, a **continuación, seleccione**el usuario de la lista de sugerencias.
5. Agregue varios usuarios hasta que haya terminado.
6. Seleccione **Guardar**y, a continuación, el usuario se agregará a la lista de administradores asignados.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Asignar un usuario a un rol de administrador desde usuarios activos

1. En el centro de administración, > vaya **a la página usuarios** [activos](https://go.microsoft.com/fwlink/p/?linkid=834822) .

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


## <a name="didnt-work-for-you"></a>¿No ha funcionado?

Es posible que no tenga los permisos correctos y no tiene acceso para asignar roles de administrador a otros usuarios. Solicite a otro administrador que lo haga por usted.

::: moniker-end

## <a name="related-articles"></a>Artículos relacionados

[Asignar roles a cuentas de usuario con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[Autorizar o quitar relaciones de asociados](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)

[Agregar una dirección de correo electrónico alternativa mediante el centro de administración de Exchange](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)

