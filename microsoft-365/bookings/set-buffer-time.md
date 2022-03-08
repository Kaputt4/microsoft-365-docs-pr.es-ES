---
title: Establecer tiempo de búfer en Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Establece el tiempo de búfer antes o después de una cita en Microsoft Bookings para permitir tiempo para limpiar o restablecer el equipo.
ms.openlocfilehash: a33159b0b5f168bbb61c88bc9b4181e05c8abbb1
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329325"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Establecer tiempo de búfer en Microsoft Bookings

Algunas de las citas pueden requerir tiempo antes o después de reunirse con el cliente para configurar, limpiar o restablecer la sala y el equipamiento. O bien, si está en el camino entre las citas de cliente, es posible que necesite tiempo para asegurarse de que usted y su equipo puedan viajar entre citas sin hacer que el cliente espere.

Puede establecer el tiempo de búfer antes de que comiencen las citas, una vez que finalicen las citas, o ambas para dar al personal el tiempo adicional que necesitan para prepararse para su próxima cita.

## <a name="set-buffer-time-defaults"></a>Establecer valores predeterminados de tiempo de búfer

Los valores predeterminados de tiempo de búfer se establecen en **la página Detalles del** servicio en Bookings. Al igual que todos los valores predeterminados de servicio establecidos en esta página, estos valores predeterminados se pueden editar para una reserva específica para satisfacer las necesidades específicas del cliente.

La configuración de tiempo de búfer se encuentra justo debajo de los **selectores** de duración predeterminada en la **página Detalles del** servicio. Para poder establecerlo para un servicio determinado, debe habilitar la configuración de tiempo del búfer seleccionando la alternancia de tiempo del búfer. Esto **hace que** aparezcan  las desplegables Antes y Después, que se usan para elegir la cantidad predeterminada de tiempo para retener antes y después de cada reserva, como se muestra aquí:

   ![Imagen de Bookings con tiempo de búfer habilitado.](../media/bookings-buffertime.png)

<!--## Buffer time and appointment timing

To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff. For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.

Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment. The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment. Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.

   ![Image of Bookings appointment call-out with buffer time showing.](../media/bookings-buffertime-callout.png)
-->

## <a name="buffer-time-and-availability"></a>Tiempo y disponibilidad del búfer

Los clientes no ven directamente y no pueden cambiar los tiempos de búfer establecidos. Sin embargo, como el tiempo de búfer se usa para calcular la duración general del servicio, los clientes lo verán a usted y a su personal relevante como reservados durante las horas de almacenamiento intermedio y de citas regulares. Los clientes también solo ven disponibilidad para usted y su personal si hay tiempo suficiente para la cita y su tiempo de búfer.

Por ejemplo, una cita de una hora con un tiempo de búfer de 15 minutos antes de la cita requiere un bloque de tiempo disponible de al menos 1 hora y 15 minutos. Por lo tanto, una cita para este servicio rellenaría un bloque de tiempo de 75 minutos en el calendario y necesita 75 minutos de disponibilidad para reservar sin conflictos.
