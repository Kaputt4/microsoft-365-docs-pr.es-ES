---
title: Quitar la licencia de un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Quitar la licencia de un buzón compartido para asignarlo a otro usuario. '
ms.openlocfilehash: 43d32744afe42a8f244160ace20c1d989f501b28
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445500"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Quitar la licencia de un buzón compartido

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Los buzones compartidos no suelen requerir una licencia. Siga estas instrucciones para quitar una licencia de un buzón de correo compartido de manera que pueda asignarla a un usuario o devolver la licencia para que no pague por una licencia que no necesite.

> [!NOTE]
> Se requiere una licencia en las siguientes situaciones:
> 1. El buzón compartido tiene más de 50 GB de almacenamiento en uso.
> 2. El buzón de correo compartido usa el archivado local.
> 3. El buzón compartido se coloca en retención por juicio.

  
## <a name="remove-the-license"></a>Quitar la licencia

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

   > [!NOTE]
   > Debe quitar la licencia de la página usuarios activos. No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario. 
  
2. Seleccione el buzón compartido.

3. Una de las pestañas **licencias y aplicaciones** , expanda **licencias** y desactive la casilla de la licencia que desea quitar.

4. Seleccione **Guardar cambios**.

5. Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.

6. Todavía está pagando por la licencia. Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

    > [!NOTE]
    > Debe quitar la licencia de la página usuarios activos. No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.

2. Seleccione el buzón compartido y, a continuación, seleccione **Editar** junto a **licencias de producto**.

3. Una página de **licencias de productos** , establezca el botón de alternancia en **desactivado** para la licencia que desea quitar.

4. Seleccione **Guardar**.

5. Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.

6. Todavía está pagando por la licencia. Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

    > [!NOTE]
    > Debe quitar la licencia de la página usuarios activos. No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.

2. Seleccione el buzón compartido y, a continuación, seleccione **Editar** junto a **licencias de producto**.

3. Una página de **licencias de productos** , establezca el botón de alternancia en **desactivado** para la licencia que desea quitar.

4. Seleccione **Guardar**.

5. Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.

6. Todavía está pagando por la licencia. Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end 

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)
