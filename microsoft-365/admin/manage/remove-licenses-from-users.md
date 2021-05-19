---
title: Cancelar la asignación de licencias a usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Obtenga información sobre cómo desasignación de licencias de cuentas de usuario.
ms.date: 07/01/2020
ms.openlocfilehash: 5ef28b3065703ec224e6426c4fdbfffdb5269b22
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537504"
---
# <a name="unassign-licenses-from-users"></a>Cancelar la asignación de licencias a usuarios

Puede desasignación de licencias de usuarios en la **página Usuarios** activos o en la **página Licencias.** El método que use depende de si desea desasignación de licencias de productos de usuarios específicos o desasignación de licencias de usuarios de un producto específico.

> [!NOTE]
> Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización. Puede [apoderarse de una suscripción de compra de autoservicio](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser un administrador global, de licencia y de usuario para desasignación de licencias. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).
- Puede [quitar licencias de cuentas de usuario con PowerShell de Office 365](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- También puede eliminar [cuentas de usuario a](../add-users/delete-a-user.md) las que se asignó una licencia para que su licencia esté disponible para otros usuarios. Al eliminar una cuenta de usuario, su licencia está disponible inmediatamente para asignarla a otra persona.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usar la página Licencias para desasignación de licencias

Al usar la página **Licencias** para desasignar licencias, se desasigna licencias para un producto específico para un máximo de 20 usuarios.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.

::: moniker-end

2. Seleccione el producto para el que desea desasignación de licencias.
3. Seleccione los usuarios para los que desea desasignación de licencias.
4. Seleccione **Unassign licenses**.
5. En el **cuadro Unassign licenses,** seleccione **Unassign**.

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usar la página Usuarios activos para desasignación de licencias

Al usar la página **Usuarios activos** para desasignación de licencias, se desasigna licencias de productos a los usuarios.

### <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione la fila del usuario para el que desea desasignación de una licencia.
3. En el panel derecho, seleccione **licencias y aplicaciones**.
4. Expanda la **sección Licencias,** desactive los cuadros de las licencias que desea desasignación y, a continuación, **seleccione Guardar cambios**.

### <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione los círculos junto a los nombres de los usuarios para los que desea desasignar licencias.
3. En la parte superior, seleccione los tres puntos (más acciones) y, a continuación, **seleccione Administrar licencias de productos**.
4. En el panel **administrar licencias de producto**, seleccione **reemplazar las asignaciones de licencias de producto existentes** \> **siguiente**.
5. En la parte inferior del panel **Reemplazar** productos **existentes,** active la casilla Quitar todas las licencias de productos de los usuarios seleccionados y, a continuación, **seleccione Reemplazar** \> **cerrar**.

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>¿Qué sucede con los datos de un usuario al quitar su licencia?

- Cuando se quita una licencia de un usuario, los datos asociados a esa cuenta se mantienen durante 30 días. Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar.
- Los archivos guardados en OneDrive para la Empresa no se eliminan a menos que el usuario se elimine del centro de administración de Microsoft 365 o se quite a través de la sincronización de Active Directory. Para obtener más información, [vea OneDrive retención y eliminación.](/onedrive/retention-and-deletion)
- Cuando se quita la licencia, el buzón del usuario ya no se puede buscar mediante una herramienta de exhibición de documentos electrónicos como búsqueda de contenido o Advanced eDiscovery. Para obtener más información, vea "Buscar buzones desconectados o sin licencia" en Búsqueda de contenido [en Microsoft 365](../../compliance/content-search.md).
- Si tiene una suscripción Enterprise, como Office 365 Enterprise E3, Exchange Online permite conservar los datos del buzón de una cuenta de usuario eliminada mediante buzones [inactivos.](../../compliance/inactive-mailboxes-in-office-365.md) Para obtener más información, vea [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Para obtener información sobre cómo bloquear el acceso de un usuario Microsoft 365 datos después de quitar su licencia y cómo obtener acceso a los datos después, vea [Remove a former employee](../add-users/remove-former-employee.md).
- Si quitas la licencia de un usuario y aún tienen Office aplicaciones instaladas, verán Errores de activación y producto sin licencia en [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usen Office aplicaciones.

## <a name="next-steps"></a>Pasos siguientes

Si no va a reasignar las licencias no [usadas](../../managed-desktop/get-started/assign-licenses.md)a otros usuarios, considere la posibilidad de quitar las licencias de la suscripción para que no pague más licencias de las que necesita. [](../../commerce/licenses/buy-licenses.md)

## <a name="related-content"></a>Contenido relacionado

[Quitar licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)\
[Asignar licencias a los usuarios](assign-licenses-to-users.md) (artículo)\
[Comprender las suscripciones y licencias en Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)
