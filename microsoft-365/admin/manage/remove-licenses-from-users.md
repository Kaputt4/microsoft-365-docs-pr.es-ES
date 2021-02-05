---
title: Cancelar la asignación de licencias a usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: Obtenga información sobre cómo desasignación de licencias de cuentas de usuario.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114482"
---
# <a name="unassign-licenses-from-users"></a>Cancelar la asignación de licencias a usuarios

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

::: moniker range="o365-worldwide"

Puede desasignación de licencias  de usuarios en la página Usuarios activos o en la **página Licencias.** El método que use dependerá de si desea desasignación de licencias de producto de usuarios específicos o desasignación de licencias de usuarios de un producto específico.

::: moniker-end

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser administrador global, de licencia y de usuario para desasignación de licencias. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).
- Puede [quitar licencias de cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- También puede eliminar [cuentas de usuario](../add-users/delete-a-user.md) a las que se asignó una licencia para que su licencia esté disponible para otros usuarios. Al eliminar una cuenta de usuario, su licencia está disponible inmediatamente para asignarla a otra persona.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usar la página Licencias para desasignación de licencias

Al usar la **página Licencias** para desasignar licencias, se desasigna licencias de un producto específico para un máximo de 20 usuarios.

1. En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.
2. Seleccione el producto para el que desea desasignación de licencias.
3. Seleccione los usuarios para los que desea desasignación de licencias.
4. Seleccione **Unassign licenses**.
5. En el **cuadro Desasignación de** licencias, seleccione **Unassign**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usar la página Usuarios activos para desasignación de licencias

Al usar la página **Usuarios activos** para desasignación de licencias, se desasigna licencias de producto a los usuarios.

### <a name="unassign-licenses-from-one-user"></a>Desasignación de licencias de un usuario
  
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione la fila del usuario para el que desea desasignación de una licencia.
3. En el panel derecho, seleccione **licencias y aplicaciones**.
4. Expanda la **sección Licencias,** desactive las casillas de las licencias que desea desasignación y, a continuación, **seleccione Guardar cambios.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Desasignación de licencias de un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.
2. Elige el usuario para el que quieres desasignación de la licencia.
3. A la derecha, en la **fila Licencias de producto,** seleccione **Editar**.
4. En el **panel Licencias de producto,** cambie el botón de alternancia a la posición Desactivado de la licencia que desea quitar para el usuario.  Por ejemplo, si se apaga la licencia de Office 365 Enterprise E3, se desasigna esa licencia y todos los servicios bajo esa licencia para ese usuario.
5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Desasignación de licencias de un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
2. Elige el usuario para el que quieres desasignación de la licencia.
3. A la derecha, en la **fila Licencias de producto,** seleccione **Editar**.
4. En el **panel Licencias de producto,** cambie el botón de alternancia a la posición Desactivado de la licencia que desea quitar para el usuario.  Por ejemplo, si se apaga la licencia de Office 365 Enterprise E3, se desasigna esa licencia y todos los servicios bajo esa licencia para ese usuario.
5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Desasignación de licencias de varios usuarios

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione los círculos junto a los nombres de los usuarios para los que desea desasignar licencias.
3. En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.
4. En el panel **administrar licencias de producto**, seleccione **reemplazar las asignaciones de licencias de producto existentes** \> **siguiente**.
5. At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Desasignación de licencias de varios usuarios

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.
2. Seleccione las casillas situadas junto a los nombres de los usuarios para los que desea desasignación de todas las licencias.
3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.
4. En el panel **Reemplazar productos existentes**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.
5. At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close** \> **.**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Desasignación de licencias de varios usuarios
  
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
2. Seleccione las casillas situadas junto a los nombres de los usuarios para los que desea desasignación de todas las licencias.
3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.
4. En el panel **Reemplazar productos existentes**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.
5. At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close** \> **.**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>¿Qué sucede con los datos de un usuario cuando quita su licencia?

- Cuando se quita una licencia de un usuario, los datos asociados con esa cuenta se mantienen durante 30 días. Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar.
- Los archivos guardados en OneDrive para la Empresa no se eliminan a menos que el usuario se elimine del Centro de administración de Microsoft 365 o se quite a través de la sincronización de Active Directory. Para obtener más información, vea [Retención y eliminación de OneDrive.](https://docs.microsoft.com/onedrive/retention-and-deletion)
- Cuando se quita la licencia, el buzón del usuario ya no se puede buscar mediante una herramienta de exhibición de documentos electrónicos como búsqueda de contenido o eDiscovery avanzado. Para obtener más información, vea "Buscar buzones desconectados o sin licencia" en Búsqueda de contenido [en Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)
- Si tiene una suscripción Enterprise, como Office 365 Enterprise E3, Exchange Online le permite conservar los datos del buzón de una cuenta de usuario eliminada mediante buzones [inactivos.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) Para obtener más información, vea Crear y administrar buzones [inactivos en Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)
- Para obtener información sobre cómo bloquear el acceso de un usuario a los datos de Microsoft 365 después de quitar su licencia y cómo obtener acceso a los datos después, consulte Quitar [un](../add-users/remove-former-employee.md)antiguo empleado.
- Si quita la licencia de un usuario y aún tiene aplicaciones de Office instaladas, verán errores de activación y producto sin licencia en [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usen aplicaciones de Office.

## <a name="next-steps"></a>Pasos siguientes

Si no va a reasignar las licencias no [usadas](../../managed-desktop/get-started/assign-licenses.md)a otros usuarios, considere la posibilidad de quitar las licencias de la suscripción para que no tenga que pagar más licencias de las que necesita. [](../../commerce/licenses/buy-licenses.md)

## <a name="related-content"></a>Contenido relacionado

[Quitar licencias de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md) (artículo)\
[Asignar licencias a usuarios](assign-licenses-to-users.md) (artículo)\
[Comprender las suscripciones y licencias de Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)