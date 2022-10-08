---
title: Informe de uso de consultas virtuales de Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
description: Obtenga información sobre cómo usar el informe de citas virtuales del conector HCE de Teams en el Centro de administración de Microsoft Teams para obtener información general sobre el uso de citas virtuales integradas en HCE en su organización.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 477562bc3b4bea61291e8bcce86dd028913ca3bc
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68063494"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Informe de uso de consultas virtuales de Teams

El Informe de uso de visitas virtuales en el centro de administración de Microsoft Teams proporciona a los administradores información general sobre la actividad de citas virtuales de Teams en su organización. Puede ver la actividad detallada de las citas virtuales programadas a través de la [aplicación Bookings](bookings-virtual-visits.md) y el [conector de Registro de estado electrónico (EHR) de Microsoft Teams](teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration).

Para ver el informe, debe ser administrador global, administrador de Teams, lector global o lector de informes.

El informe de ejemplo contiene los archivos siguientes: La información que verá en el informe depende de si tiene una licencia para la aplicación Bookings, el conector EHR de Teams o ambos.

|Pestaña |Descripción  |
|---------|---------|
|**[Consultas virtuales](#virtual-visits)**     |Muestra el número total de citas virtuales, con un desglose del número de citas programadas mediante la aplicación Bookings y las reuniones integradas en EHR de Teams realizadas desde el sistema EHR.         |
|**[Duración](#duration)**     |Muestra la duración media de las citas y el tiempo medio de espera de espera de los participantes.         |
|**[Bookings](#bookings)**     |Muestra el número de citas programadas a través de la aplicación Bookings.         |
|**[EHR](#ehr)**     |Muestra el número de citas integradas en EHR de Teams realizadas desde el sistema EHR.         |  

Use este informe para obtener información sobre las tendencias y la actividad de citas virtuales en su organización. Use esta información para conocer las tendencias de uso y así poder optimizar las citas virtuales para obtener mejores resultados empresariales.

## <a name="view-the-virtual-visits-usage-report"></a>Ver el informe de uso de las visitas virtuales

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Análisis e informes** > **Informes de uso**. En la pestaña **Ver informes**, en **Informe**, seleccione **Uso de visitas virtuales**.
2. En **Intervalo de fechas**, seleccione un intervalo de fechas de 7 días, 30 días o 90 días. A continuación, elija **Ejecutar informe**.

> [!NOTE]
> De forma predeterminada, el análisis de visitas virtuales está activado y el informe está disponible. Con este informe, concede a Microsoft permiso para recopilar datos sobre citas virtuales en su organización. Para obtener más información sobre la retención de datos, vea [Retención, eliminación y destrucción de datos en Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Si desea desactivar el informe de su organización, puede hacerlo en **Configuración** en la esquina superior derecha de la página. Esta configuración puede tardar entre 0 (cero) y 2 horas en surtir efecto después de cambiarla.

## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="virtual-visits"></a>Consultas virtuales

Los gráficos que verá aquí dependen de si tiene una licencia para la aplicación Bookings, el conector EHR de Teams o ambos. Para más información, consulte [Administración de la aplicación Bookings](/microsoftteams/bookings-app-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json) e [Integración en Cerner EHR](ehr-admin-cerner.md) o [Integración en Epic EHR](ehr-admin-epic.md).

:::image type="content" source="media/virtual-visits-usage-report-virtual-visits.png" alt-text="Captura de pantalla de la pestaña Visitas virtuales del informe de uso de las visitas virtuales que muestra las llamadas numeradas." lightbox="media/virtual-visits-usage-report-virtual-visits.png":::

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número de citas.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de citas en esa fecha.|
|**3**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, seleccione **Total de visitas virtuales a Bookings** o **Total de visitas virtuales de EHR** para ver solo la información relacionada con cada una de ellas. Al cambiar esta selección no se cambia la información de la tabla. |
|**4**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>La **hora de inicio (UTC)** es la fecha y hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>El **identificador de reunión** es el identificador único de la reunión.</li> <li>El **tiempo de espera de la sala de espera** es el tiempo entre la primera vez que un participante se une a la sala de espera hasta el momento en que un miembro del personal admite ese mismo participante o un participante diferente en la reunión.</li><li>La **duración** es la diferencia de hora entre la hora de inicio y el momento en que la última persona abandona la cita. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>El **estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **Sin presentación**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>El **tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR de Teams.</li> <li>**Asistentes** es el número total de miembros del personal y de participantes en la cita.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul> |
|**5**   |Seleccione **Configuración** para abrir el panel **Análisis de visitas virtuales**. Desde aquí, puede desactivar o activar los informes de visitas virtuales para su organización y agregar o quitar columnas de la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Puede exportar el informe a un archivo CSV para su análisis sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, seleccione **Descargar** para descargar el informe cuando esté listo.|

### <a name="duration"></a>Duración

:::image type="content" source="media/virtual-visits-usage-report-duration.png" alt-text="Captura de pantalla de la pestaña Duración del informe de uso de las visitas virtuales que muestra las llamadas numeradas." lightbox="media/virtual-visits-usage-report-duration.png":::

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número de minutos.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver la duración media de la cita o el tiempo medio de espera de la sala de espera en una fecha determinada.  |
|**3**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, seleccione **Duración media de la visita virtual** o **Promedio de tiempo de espera en la sala de espera** para ver solo la información relacionada con cada una de ellas. Al cambiar esta selección no se cambia la información de la tabla. |
|**4**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>La **hora de inicio (UTC)** es la fecha y hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>El **identificador de reunión** es el identificador único de la reunión.</li> <li>El **tiempo de espera de la sala de espera** es el tiempo entre la primera vez que un participante se une a la sala de espera hasta el momento en que un miembro del personal admite ese mismo participante o un participante diferente en la reunión.</li><li>La **duración** es la diferencia de hora entre la hora de inicio y el momento en que la última persona abandona la cita. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>El **estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **Sin presentación**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>El **tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR de Teams.</li> <li>**Asistentes** es el número total de miembros del personal y de participantes en la cita.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul>|
|**5**   |Seleccione **Configuración** para abrir el panel **Análisis de visitas virtuales**. Desde aquí, puede desactivar o activar los informes de visitas virtuales para su organización y agregar o quitar columnas de la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Puede exportar el informe a un archivo CSV para su análisis sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, seleccione **Descargar** para descargar el informe cuando esté listo.|
### <a name="bookings"></a>Bookings

Verá esta pestaña si tiene una licencia que incluye la aplicación Bookings. Para más información, consulte [Administración de la aplicación Bookings](/microsoftteams/bookings-app-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json).

:::image type="content" source="media/virtual-visits-usage-report-bookings.png" alt-text="Captura de pantalla de la pestaña Bookings del informe de uso de visitas virtuales en la que se muestran llamadas numeradas." lightbox="media/virtual-visits-usage-report-bookings.png":::

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número de citas de Bookings.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de citas de Bookings que se produjeron en esa fecha.|
|**3**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>La **hora de inicio (UTC)** es la fecha y hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>El **identificador de reunión** es el identificador único de la reunión.</li> <li>El **tiempo de espera de la sala de espera** es el tiempo entre la primera vez que un participante se une a la sala de espera hasta el momento en que un miembro del personal admite ese mismo participante o un participante diferente en la reunión.</li><li>La **duración** es la diferencia de hora entre la hora de inicio y el momento en que la última persona abandona la cita. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>El **estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **Sin presentación**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>El **tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR de Teams.</li> <li>**Asistentes** es el número total de miembros del personal y de participantes en la cita.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul>|
|**4**   |Seleccione **Configuración** para abrir el panel **Análisis de visitas virtuales**. Desde aquí, puede desactivar o activar los informes de visitas virtuales para su organización y agregar o quitar columnas de la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Puede exportar el informe a un archivo CSV para su análisis sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, seleccione **Descargar** para descargar el informe cuando esté listo.|
### <a name="ehr"></a>HCE

Verá esta pestaña si tiene una licencia que incluye el conector EHR de Teams. Para más información, consulte [Integración en Cerner EHR](ehr-admin-cerner.md) o [Integración en Epic EHR](ehr-admin-epic.md).

:::image type="content" source="media/virtual-visits-usage-report-ehr.png" alt-text="Captura de pantalla de la pestaña EHR del informe de uso de visitas virtuales que muestra las llamadas numeradas." lightbox="media/virtual-visits-usage-report-ehr.png":::

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe específico. El eje Y es el número de citas EHR.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de citas de EHR en esa fecha.|
|**3**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>La **hora de inicio (UTC)** es la fecha y hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>El **identificador de reunión** es el identificador único de la reunión.</li> <li>El **tiempo de espera de la sala de espera** es el tiempo entre la primera vez que un participante se une a la sala de espera hasta el momento en que un miembro del personal admite ese mismo participante o un participante diferente en la reunión.</li><li>La **duración** es la diferencia de hora entre la hora de inicio y el momento en que la última persona abandona la cita. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>El **estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **Sin presentación**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>El **tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR de Teams.</li> <li>**Asistentes** es el número total de miembros del personal y de participantes en la cita.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul>|
|**4**   |Seleccione **Configuración** para abrir el panel **Análisis de visitas virtuales**. Desde aquí, puede desactivar o activar los informes de visitas virtuales para su organización y agregar o quitar columnas de la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Puede exportar el informe a un archivo CSV para su análisis sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, seleccione **Descargar** para descargar el informe cuando esté listo.|

> [!NOTE]
> Si su organización desea participar en la versión preliminar privada para que los usuarios no administradores, como los responsables de la toma de decisiones empresariales, tengan acceso a este informe y lo vean, [póngase en contacto con nosotros](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Artículos relacionados

- [Citas virtuales con Teams y la aplicación Bookings](bookings-virtual-visits.md)
- [Citas virtuales con Teams: integración en Epic EHR](ehr-admin-epic.md)
- [Citas virtuales con Teams: integración en Cerner EHR](ehr-admin-cerner.md)
