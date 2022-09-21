---
title: Eliminación de un calendario de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Use el Centro de administración de Microsoft 365 o Windows PowerShell para eliminar calendarios de Bookings.
ms.openlocfilehash: b5cb74940bc68116673322c6d38e3fecd4002326
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851200"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Eliminación de un calendario de reserva en Bookings

En este artículo se explica cómo puede eliminar un calendario de reserva no deseado. Puede eliminar el calendario de reserva en el Centro de administración de Microsoft 365 o puede usar PowerShell. El calendario de Bookings es un buzón de correo en Exchange Online por lo que se elimina la cuenta de usuario correspondiente para eliminar el calendario de reserva.

> [!IMPORTANT]
> Todos los calendarios de reserva que creó en 2017 o antes deben eliminarse mediante las instrucciones de PowerShell de este tema. Todos los calendarios de reserva creados en 2018 o posterior se pueden eliminar en el Centro de administración de Microsoft 365.

El calendario de reserva es donde se almacena toda la información pertinente sobre ese calendario de reserva y los datos, incluidos:

- Información empresarial, logotipo y horas de trabajo agregadas al crear el calendario de reserva
- Personal y servicios pertinentes agregados al crear el calendario de reserva
- Todas las reservas y citas de tiempo libre agregadas al calendario de reserva una vez creadas.

> [!WARNING]
> Una vez eliminado un calendario de reserva, esta información adicional también se elimina permanentemente y no se puede recuperar.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Eliminar un calendario de reserva en el Centro de administración de Microsoft 365

1. Vaya al Centro de administración de Microsoft 365.

1. En el Centro de administración, seleccione **Usuarios**.

   ![Imagen de la interfaz de usuario de usuarios en Centro de administración de Microsoft 365.](../media/bookings-admin-center-users.png)

1. En la página **Usuarios activos** , elija el nombre del calendario de reserva que desea eliminar y, a continuación, seleccione **Eliminar usuario**.

   ![Imagen de Eliminar interfaz de usuario de usuario en Centro de administración de Microsoft 365.](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Eliminación de un calendario de reserva mediante Exchange Online PowerShell

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando para obtener una lista de los buzones de reserva del inquilino:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

3. Reemplace por \<BookingCalendarToDelete\> el nombre exacto del alias de buzón de reserva que desea eliminar permanentemente y, a continuación, ejecute el siguiente comando:

   ```powershell
   Remove-Mailbox -Identity <BookingCalendarToDelete>
   ```

   > [!IMPORTANT]
   > Tenga cuidado de escribir el nombre exacto del alias del buzón de reserva que desea eliminar permanentemente.

4. Para comprobar que el calendario se ha eliminado, ejecute el siguiente comando:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   El calendario eliminado no aparecerá en la salida.
