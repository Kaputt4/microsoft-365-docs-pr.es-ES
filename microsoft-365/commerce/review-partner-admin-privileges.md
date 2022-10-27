---
title: Revisión de los privilegios administrativos de asociados
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- empty
search.appverid: MET150
description: Obtenga información sobre cómo revisar la lista de proveedores de soluciones certificados por Microsoft (asociados) para determinar qué privilegios de administrador tienen y cómo quitar esos privilegios.
ms.date: 12/03/2021
ms.openlocfilehash: 67cafa9ebac7f641de43f0debab733d89a8b1853
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718312"
---
# <a name="review-microsoft-certified-cloud-solution-provider-partner-administrative-privileges"></a>Revisión de los privilegios administrativos de asociados del proveedor de soluciones en la nube certificados por Microsoft

Si tiene un proveedor de soluciones en la nube certificado por Microsoft (partner de revendedor), se recomienda realizar una revisión trimestral de los privilegios administrativos delegados (DAP) asignados a ellos. Asegúrese de que su organización quiere que este asociado tenga acceso a los datos de la organización y realice compras en su nombre.

> [!IMPORTANT]
> Dar DAP, que incluye permisos de administrador global, a cualquier asociado podría presentar un riesgo de seguridad. Tener demasiados administradores globales también es un riesgo para la seguridad. [Obtenga más información sobre la actividad reciente destinada a privilegios delegados](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/).

Después de aceptar un contrato DAP de un partner de revendedor, pueden asignar el rol de administrador global de su organización a sus empleados. El rol de administrador global proporciona a los empleados del asociado acceso a los datos personales de sus empleados y a otra información confidencial. También les concede permiso para realizar acciones en todo el inquilino, como las siguientes:

- Cambio de contraseñas de usuario
- Adición de usuarios con cuentas de correo electrónico
- Adición y administración de dominios web asociados a la organización

Cuando DAP está habilitado, no tiene control sobre el número de administradores globales que su asociado puede agregar. Solo puede conceder o denegar al DAP asociado (administrador global) acceso a su cuenta.

## <a name="review-and-remove-roles-from-partners"></a>Revisión y eliminación de roles de asociados

1. En el Centro de administración de Microsoft 365, vaya a la página **Configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Relaciones de asociados</a>. Los asociados con DAP tienen **un administrador global** que aparece en la columna **Roles** .
2. Para quitar el rol de administrador global de un asociado, busque el nombre del asociado que desea quitar.
3. Seleccione la fila que tiene **Reseller (Revendedor)** como **Relationship Type (Tipo de relación).**
4. En la página de detalles del asociado, seleccione **Quitar roles** y, a continuación, seleccione **Sí**.

> [!NOTE]
>
> - Si quita DAP (rol de administrador global) de un asociado, le recomendamos que se ponga en contacto con él para analizar la entrega futura del servicio. Por ejemplo, puede crear una cuenta de usuario con privilegios inferiores y compartir esa información de cuenta con su asociado. Obtenga más información sobre [cómo agregar usuarios](../admin/add-users/add-users.md) y [asignar roles de administrador](../admin/add-users/assign-admin-roles.md).
> - Incluso con el rol de administrador global eliminado, el asociado todavía puede realizar compras en su nombre. Le recomendamos que se ponga en contacto con el asociado para pedirle que quite esa capacidad en el Centro de partners.

## <a name="related-content"></a>Contenido relacionado

[Administrar relaciones de asociados](manage-partners.md) (artículo)\
[Acerca de los roles de administrador](../admin/add-users/about-admin-roles.md) (artículo)\
[Privilegios de administrador delegados en Azure AD](/partner-center/customers-revoke-admin-privileges#delegated-admin-privileges-in-azure-ad) (artículo)
