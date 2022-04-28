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
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
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
ms.date: 04/22/2022
ms.openlocfilehash: b5294bd6234c36e6040ff8cc7433c3e66b7d34b6
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093710"
---
# <a name="unassign-licenses-from-users"></a>Cancelar la asignación de licencias a usuarios

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

Al usar la página **Licencias** para anular la asignación de licencias, anula la asignación de licencias para un producto específico para un máximo de 20 usuarios.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.

::: moniker-end

2. Seleccione el producto para el que desea anular la asignación de licencias.

3. Seleccione los usuarios para los que desea anular la asignación de licencias.

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

4. En el panel **Administrar licencias de producto**, seleccione **Anular la asignación de todosGuardar** >  **cambios**.

5. En la parte inferior del panel, seleccione **Listo**.  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>¿Qué ocurre con los datos de un usuario al quitar su licencia?

- Cuando se quita una licencia de un usuario, Exchange datos en línea asociados a esa cuenta se mantienen durante 30 días. Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar.
- Los archivos guardados en OneDrive para la Empresa no se eliminan a menos que el usuario se elimine de la Centro de administración de Microsoft 365 o se quite mediante la sincronización de Active Directory. Para obtener más información, consulte [OneDrive retención y eliminación](/onedrive/retention-and-deletion).
- Cuando se quita la licencia, el buzón del usuario ya no se puede buscar mediante una herramienta de exhibición de documentos electrónicos como Búsqueda de contenido o eDiscovery (Premium). Para obtener más información, vea "Buscar buzones desconectados o sin licencia" en [Búsqueda de contenido en Microsoft 365](../../compliance/content-search.md).
- Si tiene una suscripción Enterprise, como Office 365 Enterprise E3, Exchange Online le permite conservar los datos de buzón de una cuenta de usuario eliminada mediante [buzones inactivos](../../compliance/inactive-mailboxes-in-office-365.md). Para obtener más información, consulte [Creación y administración de buzones inactivos en Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Para obtener información sobre cómo bloquear el acceso de un usuario a Microsoft 365 datos después de quitar su licencia y cómo obtener acceso a los datos posteriormente, consulte [Eliminación de un empleado anterior](../add-users/remove-former-employee.md).
- Si quita la licencia de un usuario y sigue teniendo instaladas Office aplicaciones, verá [errores de activación y producto sin licencia en Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usan aplicaciones Office.

## <a name="next-steps"></a>Siguientes pasos

Si no va a [reasignar las licencias sin usar a otros usuarios](../../managed-desktop/get-started/assign-licenses.md), considere la posibilidad [de quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) para que no pague más licencias de las que necesita.

## <a name="related-content"></a>Contenido relacionado

[Quitar licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)\
[Asignar licencias a los usuarios](assign-licenses-to-users.md) (artículo)\
[Información sobre las suscripciones y licencias en Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)
