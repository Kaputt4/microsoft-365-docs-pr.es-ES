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
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Quite una licencia de un buzón compartido para asignarla a otro usuario o devolver la licencia para que no la pague. '
ms.date: 05/11/2021
ms.openlocfilehash: 89e5e3023121bb4633d7c8c1e2f92fbecc5f3e18
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370565"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Quitar la licencia de un buzón compartido

Los buzones compartidos normalmente no requieren una licencia. Siga estas instrucciones para quitar una licencia de un buzón compartido para que pueda asignarla a un usuario o devolver la licencia para que no pague una licencia que no necesite.

> [!NOTE]
>
> Se Exchange Online una licencia del Plan 2 en los siguientes escenarios:
>
> - El buzón compartido tiene más de 50 GB de almacenamiento en uso.
> - El buzón compartido usa archivado local.
> - El buzón compartido se coloca en retención por juicio.
> - El buzón compartido tiene asignada una Microsoft 365 Defender de correo.
> 
> Para obtener instrucciones paso a paso sobre cómo asignar licencias, vea [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users). 


## <a name="remove-the-license"></a>Quitar la licencia

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

   > [!NOTE]
   > Debe quitar la licencia de la página Usuarios activos. No puede quitar la licencia de la página Buzón compartido porque las licencias son configuraciones de usuario.
  
2. Seleccione el buzón compartido.

3. Una de **las pestañas Licencias y Aplicaciones,** expanda **Licencias** y desactive la casilla de la licencia que desea quitar.

4. Seleccione **Guardar cambios**.

5. Cuando vuelva a la **página Usuarios activos,** el estado del buzón compartido será **Sin licencia.**

6. Sigue pagando por la licencia. Para dejar de pagar por ella, [quite la licencia de la suscripción](../../commerce/licenses/buy-licenses.md).

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
