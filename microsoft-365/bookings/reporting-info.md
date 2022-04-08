---
title: Reportar información para Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Obtenga información sobre cómo puede ver una vista de 4 meses de la actividad de Bookings
ms.openlocfilehash: 191194d112fe231c1a2f64245d33850ecb1266c0
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714315"
---
# <a name="reporting-info-for-bookings"></a>Información de informes para Bookings

> [!NOTE]
> Este artículo le ayuda a interactuar con la versión más reciente de Microsoft Bookings. Las versiones anteriores se retirarán en los próximos meses.

Ahora puede ver una vista de cuatro meses del calendario de Bookings en un archivo TSV. El archivo TSV le mostrará cuatro meses de datos, pero puede seleccionar períodos de cuatro meses diferentes a lo largo de un año.

Esta información de nivel de cita se puede usar para visualizar la actividad del cliente alrededor del calendario de Bookings. Los archivos TSV son archivos de valores separados por tabulaciones. Puede ver o editar un archivo como este con cualquier editor de texto o programa de hoja de cálculo, como Excel.

## <a name="see-four-months-of-booking-activity"></a>Ver cuatro meses de actividad de Booking

1. En Microsoft 365, seleccione el iniciador de aplicaciones y, a continuación, seleccione **Bookings**.

1. En la página principal Bookings, seleccione **Exportar**.

1. En la página **Exportar datos recientes** , seleccione el intervalo de fechas y seleccione **Exportar**.

1. Guarde el archivo con un nuevo nombre y especifique .xls o formato xlsx.

1. Abra el archivo para ver la vista de cuatro meses del calendario de Bookings.

1. Elija la fecha del informe y seleccione **Exportar**.

1. El informe descargado contiene un nuevo conjunto de campos además de los campos existentes.

El informe incluye los campos siguientes.

 - **Fecha y hora**
- **Nombre del cliente**
- **Correo electrónico del cliente**
- **Teléfono de cliente**
- **Dirección del cliente**
- **Plantilla**
- **Servicio**
- **Location**
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
