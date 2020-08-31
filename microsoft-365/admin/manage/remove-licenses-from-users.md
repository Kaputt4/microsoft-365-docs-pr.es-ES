---
title: Cancelar la asignación de licencias a usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Obtenga información sobre cómo cancelar la asignación de licencias desde cuentas de usuario.
ms.date: 07/01/2020
ms.openlocfilehash: 4441fd253c4cf5304562900bf31869eb4e0f21ff
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306544"
---
# <a name="unassign-licenses-from-users"></a>Cancelar la asignación de licencias a usuarios

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Puede anular la asignación de licencias de los usuarios en la página **usuarios activos** o en la página **licencias** . El método que use dependerá de si desea cancelar la asignación de licencias de producto de usuarios específicos o cancelar la asignación de licencias de usuarios de un producto específico.

::: moniker-end

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser global, licencia, administrador de usuarios para cancelar la asignación de licencias. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).
- Puede [quitar licencias de cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- También puede [eliminar cuentas de usuario a las](../add-users/delete-a-user.md) que se asignó una licencia para que su licencia esté disponible para otros usuarios. Al eliminar una cuenta de usuario, su licencia está disponible de forma inmediata para asignarla a otra persona.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usar la página licencias para cancelar la asignación de licencias

Cuando usa la página **licencias** para cancelar la asignación de licencias, puede cancelar la asignación de licencias para un producto específico para un máximo de 20 usuarios.

1. En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.
2. Seleccione el producto para el que desea cancelar la asignación de licencias.
3. Seleccione los usuarios para los que desea cancelar la asignación de licencias.
4. Seleccione **Cancelar asignación de licencias**.
5. En el cuadro cancelar la **asignación de licencias** , seleccione **quitar asignación**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usar la página usuarios activos para cancelar la asignación de licencias

Cuando se usa la página **usuarios activos** para cancelar la asignación de licencias, se desasignan las licencias de producto de los usuarios.

### <a name="unassign-licenses-from-one-user"></a>Cancelar la asignación de licencias de un usuario
  
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione la fila del usuario para la que desea quitar la asignación de una licencia.
3. En el panel derecho, seleccione **licencias y aplicaciones**.
4. Expanda la sección **licencias** , desactive las casillas de las licencias cuya asignación desea cancelar y, a continuación, seleccione **Guardar cambios**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Cancelar la asignación de licencias de un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.
2. Seleccione el usuario para el que desea quitar la asignación de la licencia.
3. En la parte derecha, en la fila **licencias de productos** , seleccione **Editar**.
4. En el panel **licencias de productos** , cambie el botón de alternancia a la posición **desactivado** para la licencia que desea quitar para el usuario. Por ejemplo, si desactiva la licencia Office 365 Enterprise E3, desasigna dicha licencia y todos los servicios de dicha licencia para ese usuario.
5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Cancelar la asignación de licencias de un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
2. Seleccione el usuario para el que desea quitar la asignación de la licencia.
3. En la parte derecha, en la fila **licencias de productos** , seleccione **Editar**.
4. En el panel **licencias de productos** , cambie el botón de alternancia a la posición **desactivado** para la licencia que desea quitar para el usuario. Por ejemplo, si desactiva la licencia Office 365 Enterprise E3, desasigna dicha licencia y todos los servicios de dicha licencia para ese usuario.
5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Cancelar la asignación de licencias de varios usuarios

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione los círculos que se encuentra junto a los nombres de los usuarios para los que desea cancelar la asignación de licencias.
3. En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.
4. En el panel **administrar licencias de producto**, seleccione **reemplazar las asignaciones de licencias de producto existentes** \> **siguiente**.
5. En la parte inferior del panel **reemplazar productos existentes** , active la casilla **quitar todas las licencias de producto de los usuarios seleccionados** y, a continuación, seleccione **reemplazar** \> **cierre**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Cancelar la asignación de licencias de varios usuarios

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.
2. Active las casillas situadas junto a los nombres de los usuarios para los que desea cancelar la asignación de licencias.
3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.
4. En el panel **Reemplazar productos existentes**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.
5. En la parte inferior del panel **reemplazar productos existentes** , active la casilla **quitar todas las licencias de producto de los usuarios seleccionados** y, a continuación, seleccione **reemplazar** \> **cerrar** \> **cierre**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Cancelar la asignación de licencias de varios usuarios
  
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
2. Active las casillas situadas junto a los nombres de los usuarios para los que desea cancelar la asignación de licencias.
3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.
4. En el panel **Reemplazar productos existentes**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.
5. En la parte inferior del panel **reemplazar productos existentes** , active la casilla **quitar todas las licencias de producto de los usuarios seleccionados** y, a continuación, seleccione **reemplazar** \> **cerrar** \> **cierre**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>¿Qué pasa con los datos de un usuario cuando quita su licencia?

- Cuando se quita una licencia de un usuario, los datos asociados con dicha cuenta se conservan durante 30 días. Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar.
- Los archivos guardados en OneDrive para la empresa no se eliminan a menos que el usuario se elimine del centro de administración de Microsoft 365 o se elimine mediante la sincronización de Active Directory. Para obtener más información, vea [retención y eliminación de OneDrive](https://docs.microsoft.com/onedrive/retention-and-deletion).
- Cuando se quita la licencia, ya no se pueden realizar búsquedas en el buzón de correo del usuario con una herramienta de eDiscovery, como la búsqueda de contenido o la exhibición avanzada de documentos electrónicos. Para obtener más información, vea "buscar buzones desconectados o no autorizados" en [búsqueda de contenido en Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Si tiene una suscripción de Enterprise, como Office 365 Enterprise E3, Exchange Online le permite conservar los datos de buzón de una cuenta de usuario eliminada mediante el uso de [buzones inactivos](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Para obtener más información, vea [crear y administrar buzones inactivos en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
- Para obtener información sobre cómo bloquear el acceso de un usuario a los datos de Microsoft 365 después de eliminar su licencia y cómo obtener acceso a los datos después, vea [quitar un antiguo empleado](../add-users/remove-former-employee.md).
- Si quita la licencia de un usuario y aún tiene aplicaciones de Office instaladas, verán [errores de activación y de producto sin licencia en Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usen aplicaciones de Office.

## <a name="next-steps"></a>Pasos siguientes

Si no va a [reasignar las licencias sin usar a otros usuarios](../../managed-desktop/get-started/assign-licenses.md), considere la posibilidad [de quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) para no pagar más licencias de las que necesita.

## <a name="related-content"></a>Contenido relacionado

[Quitar licencias de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md) (artículo) \
[Asignar licencias a usuarios](assign-licenses-to-users.md) (artículo) \
[Descripción de las suscripciones y licencias de Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)