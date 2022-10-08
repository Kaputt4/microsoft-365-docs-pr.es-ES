---
title: Cancelar la asignación de licencias a usuarios
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: sinakassaw, nicholak
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
- commerce_licensing
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: El método que use para anular la asignación de licencias de productos depende de si anula la asignación de licencias de usuarios específicos o de un producto específico.
ms.date: 07/12/2022
ms.openlocfilehash: 667cc1167bbb3f479b7aab6ab6066f8b7448d948
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68199909"
---
# <a name="unassign-microsoft-365-licenses-from-users"></a>Anulación de la asignación de licencias de Microsoft 365 de los usuarios

Puede anular la asignación de licencias de los usuarios en la página **Usuarios activos** o en la página **Licencias** . El método que use dependerá de si desea anular la asignación de licencias de productos de usuarios específicos o de anular la asignación de licencias de usuarios de un producto específico.

> [!NOTE]
>
> - Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización. Puede [apoderarse de una suscripción de compra de autoservicio](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.
>
> - Para algunas suscripciones, solo puede cancelar durante un período de tiempo limitado después de comprar o renovar la suscripción. Si la ventana de cancelación ha pasado, desactive la facturación periódica para cancelar la suscripción al final de su término.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser un administrador global, de licencia y de usuario para anular la asignación de licencias. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).
- Puede [quitar licencias de cuentas de usuario con PowerShell de Office 365](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- También puede [eliminar las cuentas de usuario a las](../add-users/delete-a-user.md) que se asignó una licencia para que su licencia esté disponible para otros usuarios. Al eliminar una cuenta de usuario, su licencia está disponible inmediatamente para asignarla a otra persona.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Uso de la página Licencias para anular la asignación de licencias

La página **Licencias** le permite asignar o cancelar la asignación de licencias para un máximo de 20 usuarios a la vez. En la página se muestran los productos de su propiedad, el número de licencias disponibles para cada producto y el número de licencias asignadas del total de licencias disponibles.

La página de **licencias** muestra un total agregado de licencias para todas las suscripciones para el mismo nombre de producto. Por ejemplo, podría tener una suscripción para Microsoft 365 Empresa Premium que tenga 5 licencias y otra suscripción que tenga 8 licencias para el mismo producto. En la página **Licencias** se muestra que tiene un total de 13 licencias para Microsoft 365 Empresa Premium en todas sus suscripciones. Esto es diferente de lo que ve en la página **Sus productos**, que muestra una fila para cada suscripción de su propiedad, incluso si son para el mismo producto.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.

::: moniker-end

2. Seleccione un producto.

3. Active las casillas de los usuarios para los que desea anular la asignación de licencias.

4. Seleccione **Anular la asignación de licencias**.

5. En el cuadro **Unassign licenses (Anular la asignación de licencias** ), seleccione **Unassign (Quitar la asignación**).

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Uso de la página Usuarios activos para anular la asignación de licencias

Cuando se usa la página **Usuarios activos** para anular la asignación de licencias, se anula la asignación de licencias de productos de los usuarios.

### <a name="unassign-licenses-from-one-user"></a>Anulación de la asignación de licencias de un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione la fila del usuario para el que desea anular la asignación de una licencia.

3. En el panel derecho, seleccione **licencias y aplicaciones**.

4. Expanda la sección **Licencias** , desactive las casillas de las licencias que desea anular la asignación y, a continuación, seleccione **Guardar cambios**.

### <a name="unassign-licenses-from-multiple-users"></a>Anulación de la asignación de licencias de varios usuarios

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione los círculos junto a los nombres de los usuarios para los que desea anular la asignación de licencias.

3. En la parte superior, seleccione **Administrar licencias de producto**.

4. En el panel **Administrar licencias de producto** , seleccione **Anular la asignación de todos los** > **cambios de guardar**.

5. En la parte inferior del panel, seleccione **Listo**.  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>¿Qué ocurre con los datos de un usuario al quitar su licencia?

- Cuando se quita una licencia de un usuario, Exchange Online datos asociados a esa cuenta se conservan durante 30 días. Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar. Sin embargo, está vinculado a la directiva de retención y el contenido que coincide con las etiquetas de retención se conserva para la detección.
- Los archivos guardados en OneDrive para la Empresa no se eliminan a menos que el usuario se elimine de la Centro de administración de Microsoft 365 o se quite mediante la sincronización de Active Directory. Para obtener más información, vea [Retención y eliminación de OneDrive](/onedrive/retention-and-deletion).
- Cuando se quita la licencia, el buzón del usuario ya no se puede buscar mediante una herramienta de exhibición de documentos electrónicos, como Búsqueda de contenido o eDiscovery (Premium). Para obtener más información, vea "Buscar buzones desconectados o sin licencia" en [Búsqueda de contenido en Microsoft 365](../../compliance/content-search.md).
- Si tiene una suscripción enterprise, como Office 365 Enterprise E3, Exchange Online le permite conservar los datos de buzón de una cuenta de usuario eliminada mediante [buzones inactivos](../../compliance/inactive-mailboxes-in-office-365.md). Para obtener más información, consulte [Creación y administración de buzones inactivos en Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Para obtener información sobre cómo bloquear el acceso de un usuario a los datos de Microsoft 365 después de quitar su licencia y cómo obtener acceso a los datos posteriormente, consulte [Eliminación de un empleado anterior](../add-users/remove-former-employee.md).
- Si quita la licencia de un usuario y sigue teniendo instaladas aplicaciones de Office, verá [errores de activación y producto sin licencia en Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usan aplicaciones de Office.

## <a name="next-steps"></a>Pasos siguientes

Si no va a [reasignar las licencias sin usar a otros usuarios](assign-licenses-to-users.md), considere la posibilidad [de quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) para que no pague más licencias de las que necesita.

## <a name="related-content"></a>Contenido relacionado

[Quitar licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)\
[Asignar licencias a los usuarios](assign-licenses-to-users.md) (artículo)\
[Información sobre las suscripciones y licencias en Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)
