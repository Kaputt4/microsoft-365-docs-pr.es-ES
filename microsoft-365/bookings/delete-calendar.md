---
title: Eliminar un calendario de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Use el centro de administración de Microsoft 365 o Windows PowerShell para eliminar calendarios de reservas.
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422447"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Eliminar un calendario de reserva en las reservas

En este artículo se explica cómo se puede eliminar un calendario de reserva no deseado. Puede eliminar el calendario de reserva en el centro de administración de Microsoft 365 o puede usar PowerShell. El calendario de reservas es un buzón de correo en Exchange Online, por lo que se elimina la cuenta de usuario correspondiente para eliminar el calendario de reserva.

> [!IMPORTANT]
> Todos los calendarios de reserva que creó en 2017 o antes deben eliminarse con las instrucciones de PowerShell de este tema. Todos los calendarios de reserva creados en 2018 o posteriores pueden eliminarse en el centro de administración de Microsoft 365.

El calendario de reserva es donde se almacena toda la información relevante sobre el calendario y los datos de reserva, entre los que se incluyen:

- Información de la empresa, logotipo y horas laborales agregadas al crear el calendario de reserva
- Personal y servicios relevantes agregados cuando se creó el calendario de reserva
- Todas las reservas y las citas de tiempo libre agregadas al calendario de reserva una vez que se creó.

> [!WARNING]
> Una vez que se elimina un calendario de reserva, esta información adicional también se elimina permanentemente y no se puede recuperar.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Eliminar un calendario de reserva en el centro de administración de Microsoft 365

1. Vaya al Centro de administración de Microsoft 365.

1. En el Centro de administración, seleccione **Usuarios**.

   ![Imagen de la interfaz de usuario de Microsoft en el centro de administración de 365](../media/bookings-admin-center-users.png)

1. En la página **Usuarios activos**, elija los nombres de los usuarios que quiera eliminar y después seleccione **Eliminar usuario**.

   ![Imagen de la interfaz de usuario de eliminación en el centro de administración de Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Eliminar un calendario de reserva con Exchange Online PowerShell

Consulte [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para obtener los requisitos previos y las instrucciones para conectarse a PowerShell de Exchange Online.

Para realizar estos pasos, debe usar una ventana de comandos de PowerShell de Microsoft que haya ejecutado eligiendo la opción "ejecutar como administrador".

1. Escriba el siguiente comando:

   ```PowerShell
    $user = get-credential
   ```

1. Cuando se le pida, inicie sesión con las credenciales de administrador de inquilinos en el inquilino de Microsoft 365 que hospeda el calendario de reserva que desea eliminar de forma permanente.

1. En el símbolo del sistema de PowerShell, escriba este comando:

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. Escriba el siguiente comando:

   ```PowerShell
    Import-PSSession $s
   ```

1. Una vez que este comando haya terminado el procesamiento, escriba el siguiente comando para obtener una lista de los buzones de reserva del espacio empresarial:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. Escriba el siguiente comando:

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Tenga cuidado de escribir el nombre exacto del alias del buzón de reserva que desea eliminar de forma permanente.

1. Para comprobar que el calendario se ha eliminado, escriba el siguiente comando:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   El calendario eliminado no aparecerá en el resultado.
