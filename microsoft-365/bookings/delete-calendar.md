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
description: Use el Centro de administración de Microsoft 365 o Windows PowerShell para eliminar Bookings calendarios.
ms.openlocfilehash: 5b91a6b2c3d3d0637a017b0250ec45394958e147
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714381"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Eliminar un calendario de reserva en Bookings

> [!NOTE]
> Este artículo le ayuda a interactuar con la versión más reciente de Microsoft Bookings. Las versiones anteriores se retirarán en los próximos meses.

En este artículo se explica cómo puede eliminar un calendario de reserva no deseado. Puede eliminar el calendario de reserva en el Centro de administración de Microsoft 365 o puede usar PowerShell. El calendario de Bookings es un buzón en Exchange Online por lo que se elimina la cuenta de usuario correspondiente para eliminar el calendario de reserva.

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

1. En la página **Usuarios activos**, elija los nombres de los usuarios que quiera eliminar y después seleccione **Eliminar usuario**.

   ![Imagen de Eliminar interfaz de usuario de usuario en Centro de administración de Microsoft 365.](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Eliminación de un calendario de reserva mediante Exchange Online PowerShell

Consulte [Conectar para Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2) para conocer los requisitos previos y las instrucciones para conectarse a Exchange Online PowerShell.

Para realizar estos pasos, debe usar una ventana de comandos de Microsoft PowerShell activa que haya ejecutado eligiendo la opción "Ejecutar como administrador".

1. En una ventana de PowerShell, cargue el módulo EXO V2 ejecutando el comando siguiente:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > Si ya [instaló el módulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), el comando anterior funcionará como está escrito.
   
2. El comando que necesita ejecutar usa la sintaxis siguiente:

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ es su cuenta en el formato del nombre principal de usuario (por ejemplo, `john@contoso.com`).

3. Cuando se le solicite, inicie sesión con las credenciales de administrador de inquilinos en el inquilino de Microsoft 365 que hospeda el calendario de reserva que desea eliminar permanentemente.

4. Una vez que este comando haya terminado de procesarse, escriba el siguiente comando para obtener una lista de los buzones de reserva en el inquilino:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. Escriba el siguiente comando:

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Tenga cuidado de escribir el nombre exacto del alias del buzón de reserva que desea eliminar permanentemente.

6. Para comprobar que el calendario se ha eliminado, escriba el siguiente comando:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   El calendario eliminado no aparecerá en la salida.
