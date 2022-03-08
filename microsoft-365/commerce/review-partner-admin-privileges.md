---
title: Revisar privilegios administrativos de asociado
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
search.appverid: MET150
description: Obtenga información sobre cómo revisar la lista de proveedores de soluciones certificados por Microsoft (partners) para determinar qué privilegios de administrador tienen y cómo quitar esos privilegios.
ms.date: 12/03/2021
ms.openlocfilehash: 067716689bd82e67dda357d675383ef2541b1dc3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318429"
---
# <a name="review-partner-administrative-privileges"></a>Revisar privilegios administrativos de asociado

Si tiene un proveedor de soluciones en la nube certificado por Microsoft (partner revendedor), le recomendamos que realice una revisión trimestral de los privilegios administrativos delegados (DAP) asignados a ellos. Asegúrese de que su organización quiere que este partner tenga acceso a los datos de su organización y realice compras en su nombre.

> [!IMPORTANT]
> Dar DAP, que incluyen permisos de administrador global, a cualquier partner puede presentar un riesgo de seguridad. Tener demasiados administradores globales también es un riesgo para la seguridad. [Obtenga más información sobre la actividad reciente dirigida a privilegios delegados](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/).

Después de aceptar un contrato dap de un partner de revendedor, pueden asignar el rol de administrador global de la organización a sus empleados. El rol de administrador global proporciona a los empleados del partner acceso a los datos personales de sus empleados y otra información confidencial. También les da permiso para realizar acciones en todo el espacio empresarial, como las siguientes acciones:

- Cambio de contraseñas de usuario
- Agregar usuarios con cuentas de correo electrónico
- Agregar y administrar dominios web asociados a su organización

Cuando DAP está habilitado, no tienes control sobre el número de administradores globales que tu partner puede agregar. Solo puede conceder o denegar el acceso dap asociado (administrador global) a su cuenta.

## <a name="review-and-remove-roles-from-partners"></a>Revisar y quitar roles de asociados

1. En el Centro de administración de Microsoft 365, vaya a la **página Configuración** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">relaciones departner</a>. Los asociados con DAP tienen **el administrador global** enumerado en la **columna Roles** .
2. Para quitar el rol de administrador global de un partner, busque el nombre del partner que desea quitar.
3. Seleccione la fila que tiene **Reseller** como **tipo de relación**.
4. En la página de detalles del partner, seleccione **Quitar roles** y, a continuación, seleccione **Sí**.

> [!NOTE]
>
> - Si quita DAP (rol de administrador global) de un partner, se recomienda ponerse en contacto con ellos para analizar la futura entrega de servicios. Por ejemplo, puede crear una cuenta de usuario con privilegios inferiores y compartir esa información de cuenta con su partner. Obtenga más información sobre [cómo agregar usuarios](../admin/add-users/add-users.md) y [asignar roles de administrador](../admin/add-users/assign-admin-roles.md).
> - Incluso con el rol de administrador global eliminado, el partner aún puede realizar compras en su nombre. Se recomienda ponerse en contacto con el partner para pedirle que quite esa capacidad en el Centro de partners.

## <a name="related-content"></a>Contenido relacionado

[Administrar relaciones de partner](manage-partners.md) (artículo)\
[Acerca de los roles de administrador](../admin/add-users/about-admin-roles.md) (artículo)\
[Privilegios de administrador delegados en Azure AD](/partner-center/customers-revoke-admin-privileges#delegated-admin-privileges-in-azure-ad) (artículo)
