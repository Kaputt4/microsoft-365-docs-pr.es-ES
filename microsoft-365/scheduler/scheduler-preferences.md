---
title: Ajustar las preferencias de programación para Scheduler para Microsoft 365 Información general
ms.author: shivb
author: shivbijlani
manager: charlle
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Obtenga información sobre cómo ajustar las preferencias de programación de Scheduler para Microsoft 365.
ms.openlocfilehash: 4c6bf31472f9237f82905ce36f7db534a99896b0
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65670393"
---
<a name="scheduling-preferences"></a>Preferencias de programación
======================

Scheduler tiene en cuenta varias preferencias Outlook para programar una reunión para un organizador. Los cambios en la configuración de sus preferencias a través de Outlook clientes se reflejarán automáticamente en la forma en que Scheduler controla las solicitudes posteriores enviadas a Cortana. Por ejemplo, si un organizador cambia su preferencia de zona horaria en la página Configuración de Outlook Web, todas las solicitudes posteriores del organizador tendrán como valor predeterminado el nuevo valor de zona horaria.

<a name="supported-settings"></a>Configuración compatibles
------------------

<a name="time-zone"></a>Zona horaria
---------

Zona horaria que se usa al determinar una hora adecuada para programar reuniones. Consulte [la documentación sobre agregar, quitar o cambiar zonas horarias](https://support.microsoft.com/en-us/office/add-remove-or-change-time-zones-5ab3e10e-5a6c-46af-ab48-156fedf70c04) .

<a name="work-hours-and-days"></a>Horas y días laborables
-------------------

Para la mayoría de los tipos de reunión, Scheduler programará una hora según las preferencias de la semana laboral y el horario de reunión del organizador. Consulte [Cambiar las horas de trabajo y los días en Outlook](https://support.microsoft.com/en-us/office/change-your-work-hours-and-days-in-outlook-a27f261d-0681-415f-8ac1-388ab21e833f) documentación.

<a name="online-meetings"></a>Conferencias en línea
---------------

Puede activar una opción Calendario para que todas las reuniones que programe desde Outlook y Scheduler se celebren en línea con los detalles de la conferencia. Scheduler admite actualmente Teams y Skype como proveedores de reuniones. Consulte [La documentación sobre la realización de todas las reuniones Teams reuniones](https://support.microsoft.com/en-us/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f#bkmk_makeallteamsmtngs).

<a name="default-meeting-duration"></a>Duración predeterminada de la reunión
------------------------

Si el organizador no especifica la duración de la reunión deseada en la solicitud, Scheduler usará la duración de la reunión preferida para la solicitud. Esta configuración solo está disponible en el cliente Windows Outlook.

1. Haga clic en **Opciones** **de archivo.** >  

2. Seleccione **Calendario** en el **panel de navegación**.

3. La configuración de duración predeterminada se encuentra en **Opciones** **de calendario**.

![Calendario de Outlook cuadro de diálogo de opciones en Windows. Configure el tiempo de trabajo, la duración predeterminada y acorte las opciones de reuniones para que Scheduler las use como valores predeterminados.](../media/OutlookOptions.png)

<a name="avoid-back-to-back-meetings"></a>Evitar reuniones back-to-back
---------------------------

Outlook ahora tiene una configuración que inicia automáticamente las reuniones tarde o finaliza las reuniones antes de tiempo para evitar las reuniones inversas. Si se establece, Scheduler también acortará la duración de la reunión según la configuración de preferencia. Consulte [Cambio de la longitud predeterminada de la reunión](https://techcommunity.microsoft.com/t5/hybrid-work/change-default-meeting-length-in-outlook-avoid-back-to-back/m-p/1247361) en Outlook documentación.

##<a name="additional-note"></a>Nota adicional

- Si usa el cliente de Windows, debe establecer la siguiente opción para asegurarse de que las preferencias se sincronizan entre Scheduler y otros clientes Outlook:

![Calendario de Outlook cuadro de diálogo de opciones en Windows. Active esta opción para habilitar "Almacenar mi configuración de Outlook en la nube".](../media/OutlookOptions2.png)
