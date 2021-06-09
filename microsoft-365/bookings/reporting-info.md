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
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887246"
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
- **Location**
- **Duración (minutos)**
- **Tipo de evento**

El informe mejorado ahora contiene los siguientes campos.

- **Tipo de precios**   Tipo de precio predeterminado establecido para un servicio al crear el servicio.
- **Precio**   Precio correspondiente al tipo de precio elegido.
- **Moneda**   Tipo de moneda establecido para una empresa.
- **Asistentes de Cc**   Los destinatarios que recibirán las notificaciones por correo electrónico de una reserva. Esto se puede especificar desde la aplicación Teams al crear una reserva.
- **Recuento de asistentes registrados**   Cuántos clientes reservaron un servicio de reserva de grupo.
- **Notificaciones de texto habilitadas**   Si los clientes pueden recibir SMS notificaciones relacionadas con texto.
- **Campos personalizados**   Todas las preguntas y respuestas relacionadas con una única reserva se combinan en este campo.
- **Id. de reserva**   Esto es útil para identificar las mismas reservas de un servicio de grupo.
