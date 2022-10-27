---
title: Establecer el tiempo de búfer de Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Establezca el tiempo de búfer antes o después de una cita en Microsoft Bookings para permitir tiempo para limpiar o restablecer el equipo.
ms.openlocfilehash: 02586ff6ad6d1676c4a596a4eca6eb98959c4005
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68726539"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Establecer el tiempo de búfer en Microsoft Bookings

Algunas de las citas pueden requerir tiempo antes o después de reunirse con el cliente para configurar, limpiar o restablecer la habitación y el equipo. O bien, si está en camino entre las citas del cliente, es posible que necesite tiempo para asegurarse de que usted y su equipo puedan viajar entre citas sin hacer que el cliente espere.

Puede establecer el tiempo de búfer antes de que comiencen las citas, después de que finalicen las citas, o ambas para dar al personal el tiempo adicional que necesitan para prepararse para su próxima cita.

## <a name="set-buffer-time-defaults"></a>Establecimiento de valores predeterminados de tiempo de búfer

Los valores predeterminados de tiempo de búfer se establecen en la página **Detalles del servicio** de Bookings. Al igual que todos los valores predeterminados de servicio establecidos en esta página, estos valores predeterminados los puede editar usted para que una reserva específica satisfaga las necesidades específicas del cliente.

La configuración de tiempo de búfer se puede encontrar en la página **Detalles del servicio** . Antes de que se pueda establecer para un servicio determinado, debe habilitar la configuración de tiempo de búfer seleccionando el botón de alternancia de tiempo del búfer. Esto hace que aparezcan las listas desplegables **Antes** y **Después** , que se usan para elegir la cantidad predeterminada de tiempo que se debe esperar antes y después de cada reserva, como se muestra aquí:

   ![Imagen de Bookings con el tiempo de búfer habilitado.](../media/bookings-buffertime.png)

<!--## Buffer time and appointment timing

To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff. For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.

Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment. The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment. Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.

   ![Image of Bookings appointment call-out with buffer time showing.](../media/bookings-buffertime-callout.png)
-->

## <a name="buffer-time-and-availability"></a>Tiempo de búfer y disponibilidad

Los clientes no ven directamente y no pueden cambiar los tiempos de búfer que establezca. Sin embargo, dado que el tiempo de búfer se usa para calcular la duración general del servicio, los clientes verán que usted y su personal pertinente se reservan durante el búfer y las horas de citas regulares. Los clientes también solo ven disponibilidad para usted y su personal si hay suficiente tiempo para la cita y su tiempo de búfer.

Por ejemplo, una cita de una hora con un tiempo de búfer de 15 minutos antes de la cita requiere un bloque de tiempo disponible de al menos 1 hora y 15 minutos. Por lo tanto, una cita para este servicio rellenaría un bloque de tiempo de 75 minutos en su calendario y necesita 75 minutos de disponibilidad para reservar sin conflictos.
