---
title: Quitar la licencia de un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: sinakassaw, nicholak
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
- commerce_licensing
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Quite una licencia de un buzón compartido para asignarla a otro usuario o devolverla para que no la pague. '
ms.date: 04/22/2022
ms.openlocfilehash: 94b9a6948d6ecbd3d6e34ae9e3e8402f4c1e0d36
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68166799"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Quitar la licencia de un buzón compartido

Los buzones compartidos normalmente no requieren una licencia. Siga estas instrucciones para quitar una licencia de un buzón compartido de modo que pueda asignarla a un usuario o devolverla para que no pague una licencia que no necesite.

> [!NOTE]
>
> Se requiere una licencia Exchange Online plan 2 en los escenarios siguientes:
>
> - El buzón compartido tiene más de 50 GB de almacenamiento en uso.
> - El buzón compartido usa el archivado local.
> - El buzón compartido se coloca en suspensión por juicio.
> 
> Para obtener instrucciones paso a paso sobre cómo asignar licencias, consulte Asignación de [licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users). 


## <a name="remove-the-license"></a>Quitar la licencia

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

   > [!NOTE]
   > Debe quitar la licencia de la página Usuarios activos. No puede quitar la licencia de la página Buzón compartido porque las licencias son la configuración del usuario.
  
2. Seleccione el buzón compartido.

3. Una de las pestañas **Licencias y aplicaciones** , expanda **Licencias** y desactive la casilla de la licencia que desea quitar.

4. Seleccione **Guardar cambios**.

5. Cuando vuelva a la página **Usuarios activos** , el estado del buzón compartido será **Sin licencia**.

6. Sigue pagando por la licencia. Para dejar de pagar por ella, [quite la licencia de la suscripción](../../commerce/licenses/buy-licenses.md).

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
