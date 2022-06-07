---
title: Ajustar las preferencias de programación para Scheduler for Microsoft 365 Overview
ms.author: shivb
author: shivbijlani
manager: charlle
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Obtenga información sobre cómo ajustar las preferencias de programación para Scheduler para Microsoft 365.
ms.openlocfilehash: e6b6f4426b173bced90fcc8f2a705bc3e48cd09e
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "65923389"
---
# <a name="scheduling-preferences-used-by-scheduler"></a>Preferencias de programación usadas por Scheduler

Scheduler usa varias preferencias de Outlook para programar una reunión para un organizador. Cualquier cambio en la configuración de preferencias en los clientes de Outlook afectará a cómo scheduler controla las solicitudes enviadas a Cortana. Por ejemplo, si un organizador cambia la preferencia de zona horaria en la página de configuración de Outlook Web, todas las solicitudes del organizador que siguen tendrán como valor predeterminado la nueva zona horaria.

## <a name="supported-settings"></a>Configuración admitida

- **Zona horaria**. El programador de zona horaria usa para determinar una hora adecuada para las reuniones. Consulte [Agregar, quitar o cambiar zonas horarias](https://support.microsoft.com/en-us/office/add-remove-or-change-time-zones-5ab3e10e-5a6c-46af-ab48-156fedf70c04) para obtener información.

- **Horas de trabajo y días**. Para la mayoría de los tipos de reunión, Scheduler selecciona una hora según las preferencias de la semana de trabajo y las horas de reunión del organizador. Vea [Cambiar las horas y días laborales en Outlook](https://support.microsoft.com/en-us/office/change-your-work-hours-and-days-in-outlook-a27f261d-0681-415f-8ac1-388ab21e833f) para obtener información.

- **Reuniones en línea**. Puede activar una opción calendario para que todas las reuniones que programe desde Outlook y Scheduler se celebren en línea con los detalles de la conferencia. Scheduler admite actualmente Teams y Skype como proveedores de reuniones. Consulte [Realización de todas las reuniones de Teams](https://support.microsoft.com/en-us/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f#bkmk_makeallteamsmtngs) para obtener información.

- **Duración predeterminada de la reunión**. Si el organizador no especifica la duración de la reunión deseada en la solicitud, Scheduler usará la duración de la reunión preferida para la solicitud. Esta configuración solo está disponible en el cliente de Windows Outlook.

   1. Seleccione **Opciones** **de archivo** >  para ver el cuadro de diálogo Opciones de Outlook.

   2. Seleccione **Calendario** en la lista de la izquierda del cuadro de diálogo.

   3. En Configuración de opciones de calendario a la derecha del cuadro de diálogo, seleccione **Duración predeterminada para nuevas citas y reuniones**.

      :::image type="content" source="../media/OutlookOptions.png" alt-text="Cuadro de diálogo Opciones de calendario de Outlook en Windows, donde puede configurar el tiempo de trabajo, la duración predeterminada de la reunión y seleccionar acortar las reuniones para que scheduler las use.":::

- **Evite las reuniones back-to-back**. Una configuración de Outlook puede iniciar reuniones tarde o finalizar las reuniones antes de tiempo para evitar las reuniones back-to-back. Además, Scheduler puede acortar la duración de la reunión según la preferencia que establezca. Consulte [Cambio de la longitud predeterminada de la reunión](https://techcommunity.microsoft.com/t5/hybrid-work/change-default-meeting-length-in-outlook-avoid-back-to-back/m-p/1247361) para obtener información.

> [!NOTE]
> Si usa el cliente de Windows, debe seleccionar **Almacenar la configuración de Outlook en la nube** para sincronizar sus preferencias entre Scheduler y otros clientes de Outlook.
> :::image type="content" source="../media/OutlookOptions2.png" alt-text="Cuadro de diálogo Opciones de calendario de Outlook en Windows. Seleccione Almacenar la configuración de Outlook en la nube para sincronizar las preferencias de programación entre clientes.":::
