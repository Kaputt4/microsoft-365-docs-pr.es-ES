---
title: Visualización de la información del calendario de Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.collection:
- scotvorg
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Obtenga información sobre cómo puede ver una vista de 4 meses de la actividad de Bookings.
ms.openlocfilehash: 4ca1a4c94ce14a8d673ff88be49dbb67b013a9c3
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68207828"
---
# <a name="reporting-info-for-bookings"></a>Información de informes para Bookings

Ahora puede ver una vista de cuatro meses del calendario de Bookings en un archivo TSV. El archivo TSV le mostrará cuatro meses de datos, pero puede seleccionar períodos de cuatro meses diferentes a lo largo de un año.

Esta información de nivel de cita se puede usar para visualizar la actividad del cliente en torno a su calendario de Bookings. Los archivos TSV son archivos de valores separados por tabulaciones. Puede ver o editar un archivo como este con cualquier editor de texto o programa de hoja de cálculo, como Excel.

## <a name="see-four-months-of-booking-activity"></a>Ver cuatro meses de actividad de Booking

1. En Microsoft 365, seleccione el iniciador de aplicaciones y, a continuación, seleccione **Bookings**.

1. En la página principal de Bookings, seleccione **Exportar**.

1. En la página **Exportar datos recientes** , seleccione el intervalo de fechas y seleccione **Exportar**.

1. Guarde el archivo con un nuevo nombre y especifique .xls o formato xlsx.

1. Abra el archivo para ver la vista de cuatro meses del calendario de Bookings.

1. Elija la fecha del informe y seleccione **Exportar**.

1. El informe descargado contiene un nuevo conjunto de campos además de los campos existentes.

El informe incluye los campos siguientes.

 - **Fecha y hora**
- **Nombre del cliente**
- **Email de clientes**
- **Teléfono del cliente**
- **Dirección del cliente**
- **Plantilla**
- **Servicio**
- **Ubicación**
- **Duración (minutos)**
- **Tipo de evento**

El informe mejorado contiene ahora los campos siguientes.

- **Tipo de precios**   Tipo de tarifa predeterminado establecido para un servicio al crear el servicio.
- **Precio**   Precio correspondiente al tipo de precios elegido.
- **Moneda**   Tipo de moneda establecido para una empresa.
- **Asistentes de Cc**   Destinatarios que recibirán las notificaciones por correo electrónico de una reserva. Esto se puede especificar desde la aplicación Teams al crear una reserva.
- **Recuento de asistentes inscritos**   Cuántos clientes han reservado un servicio de reserva de grupos.
- **Notificaciones de texto habilitadas**   Si los clientes pueden recibir notificaciones relacionadas con texto SMS.
- **Campos personalizados**   Todas las preguntas y respuestas relacionadas con una única reserva se combinan en este campo.
- **Id. de reserva**   Esto resulta útil para identificar las mismas reservas de un servicio de grupo.
- **Seguimiento de datos**   Realice un seguimiento de las métricas de los identificadores de campaña que usa en las campañas de marketing.
