---
title: Reportar información para Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Obtenga información sobre cómo puede ver una vista de 4 meses de su actividad de Bookings
ms.openlocfilehash: 8fc8a41a982135550ae711e435905c9bd39460994b1f6757b633aea49a7a48a0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53838216"
---
# <a name="reporting-info-for-bookings"></a>Información de informes para Bookings

Ahora puede ver una vista de cuatro meses del calendario de Bookings en un archivo TSV. El archivo TSV le mostrará cuatro meses de datos, pero puede seleccionar diferentes períodos de cuatro meses a lo largo de un año.

Esta información de nivel de cita se puede usar para visualizar la actividad del cliente alrededor del calendario de Bookings. Los archivos TSV son archivos de valores separados por tabulaciones. Puedes ver o editar un archivo como este con cualquier editor de texto u programa de hoja de cálculo, como Excel.

## <a name="see-four-months-of-booking-activity"></a>Ver cuatro meses de actividad de Booking

1. En el panel del calendario de Bookings, **seleccione Exportar más datos como TSV**.

:::image type="content" source="../media/bookings-activities.png" alt-text="Captura de pantalla: 4 meses de actividad de Bookings":::

1. Guarde el archivo con un nuevo nombre y especifique .xls o formato xlsx.

1. Abra el archivo para ver la vista de cuatro meses del calendario de Bookings.

1. Elija la fecha del informe y seleccione **Exportar**.

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="Captura de pantalla: elija un intervalo de tiempo y exporte datos al archivo TSV.":::

1. El informe descargado contiene un nuevo conjunto de campos además de los campos existentes.

El informe incluye los siguientes campos.

 - **Fecha y hora**
- **Nombre del cliente**
- **Correo electrónico del cliente**
- **Clientes Teléfono**
- **Dirección del cliente**
- **Plantilla**
- **Servicio**
- **Ubicación**
- **Duración (minutos)**
- **Tipo de evento**

El informe mejorado ahora contiene los siguientes campos.

- **Tipo de precios**   Tipo de precio predeterminado establecido para un servicio al crear el servicio.
- **Precio**   Precio correspondiente al tipo de precio elegido.
- **Moneda**   Tipo de moneda establecido para una empresa.
- **Asistentes de Cc**   Los destinatarios que recibirán las notificaciones por correo electrónico de una reserva. Esto se puede especificar desde la aplicación Teams al crear una reserva.
- **Recuento de asistentes registrados**   Cuántos clientes reservaron un servicio de reserva de grupo.
- **Notificaciones de texto habilitadas**   Si los clientes pueden recibir notificaciones relacionadas con texto SMS.
- **Campos personalizados**   Todas las preguntas y respuestas relacionadas con una única reserva se combinan en este campo.
- **Id. de reserva**   Esto es útil para identificar las mismas reservas de un servicio de grupo.
