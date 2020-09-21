---
title: Establecer el tiempo de búfer en Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Establezca el tiempo de búfer antes o después de una cita en Microsoft Books para dejar tiempo para limpiar o restablecer el equipo.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962352"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Establecer el tiempo de búfer en Microsoft bookings

Es posible que algunas de sus citas necesiten tiempo antes o después de reunirse con el cliente para configurar, limpiar o restablecer la sala y el equipamiento. O, si está de viaje entre las citas de los clientes, es posible que necesite tiempo para asegurarse de que usted y su equipo puedan viajar entre las citas sin necesidad de que el cliente espere.

Puede establecer el tiempo de búfer antes de que se inicien las citas, tras la finalización de las citas o ambos para dar al personal el tiempo adicional necesario para preparar la próxima cita.

## <a name="set-buffer-time-defaults"></a>Establecer los valores predeterminados de tiempo de búfer

Los valores predeterminados de tiempo de búfer se establecen en la página **detalles del servicio** en reservas. Como todos los valores predeterminados de servicio establecidos en esta página, puede editar estos valores predeterminados para una reserva específica para satisfacer las necesidades específicas de los clientes.

La configuración de tiempo de búfer se puede encontrar justo debajo de los selectores de **duración predeterminados** en la página **detalles del servicio** . Antes de que se pueda establecer para un servicio determinado, debe habilitar la configuración de tiempo de búfer seleccionando el botón de alternancia tiempo de búfer. Esto hace que aparezcan las listas desplegables **antes** y **después** de, que se usan para elegir la cantidad de tiempo predeterminada para mantener antes y después de cada reserva, tal como se muestra aquí:

   ![Imagen de reservas con tiempo de búfer habilitado](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Tiempo de búfer y calendario de citas

Para evitar confusiones sobre cuándo los clientes esperan reunirse con usted, Books muestra el tiempo de búfer y la hora de la cita real (la hora a la que los clientes esperan reunirse con usted) en el calendario y en las confirmaciones de correo electrónico y los recordatorios para el personal pertinente. Por ejemplo, a continuación se muestra lo que vería en las reservas para una cita con un cliente que incluye 15 minutos de tiempo de búfer antes de la cita.

Tenga en cuenta que el evento en sí (a la izquierda en la imagen siguiente) muestra un sombreado más claro para la hora del búfer y el sombreado más oscuro para la cita real del cliente. La llamada de cita (que se abre al seleccionar el evento) indica específicamente que la cita es de 9:00AM a 10:00AM con Katie Katie e incluye 15 minutos de tiempo de búfer antes de la cita y 0 minutos después de la cita. Confirmaciones y recordatorios para que el personal haga referencia de forma similar a la hora de la cita y del búfer, mientras el cliente solo obtendría confirmaciones y avisos que hagan referencia a un 9:00AM a 10:00AM hora de la cita.

   ![Imagen de la llamada de cita de reservas con tiempo de búfer visible](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Tiempo y disponibilidad de búfer

Los clientes no ven directamente y no pueden cambiar las horas de búfer que establezca. Sin embargo, dado que el tiempo de búfer se usa para calcular la duración global del servicio, los clientes verán a usted y a su personal pertinente como reservada durante las horas de citas regulares y de búfer. Los clientes también ven la disponibilidad para usted y su personal si hay tiempo suficiente para la cita y el tiempo de búfer.

Por ejemplo, una cita de una hora con un tiempo en el búfer de la cita previa a la cita de 15 minutos requiere un bloque de tiempo disponible de al menos 1 hora y 15 minutos. Por lo tanto, una cita para este servicio debería completar un bloque de tiempo de 75 minutos en el calendario y necesitará 75 minutos de disponibilidad para reservar el libro sin conflictos.
