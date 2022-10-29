---
title: Citas virtuales con Microsoft Teams y la aplicación Bookings
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-frontline
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
- highpri
- EngageScoreSep2022
ms.reviewer: ''
description: Obtenga información sobre cómo programar, administrar y realizar citas virtuales mediante la aplicación Bookings en Teams.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: cb7407e57a8624eeb0327ae9fcb16b55be68ea49
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785097"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>Citas virtuales con Microsoft Teams y la aplicación Bookings

## <a name="overview"></a>Información general

La [aplicación Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) en Microsoft Teams proporciona a las organizaciones una forma sencilla de programar y administrar citas virtuales para el personal y los asistentes. Úsela para programar citas como visitas sanitarias, consultas financieras, entrevistas, atención al cliente, accesorios y consultas virtuales, horas de oficina educativas y mucho más.

La aplicación Bookings facilita la administración de demandas de programación complejas de cualquier organización. Los programadores pueden administrar calendarios de varios departamentos y de personal, así como las comunicaciones con asistentes internos y externos, desde una sola experiencia.

Las citas virtuales se realizan a través de reuniones de Microsoft Teams, que ofrecen sólidas funcionalidades para videoconferencias. Por ejemplo, un médico puede compartir su pantalla y revisar los resultados de las pruebas con un paciente. O bien, un asesor bancario puede solicitar firmas electrónicas en documentos, lo que le permite cerrar transacciones de forma remota.

Cada cita virtual incluye un vínculo de reunión de Teams que se envía a los asistentes por correo electrónico, donde pueden unirse fácilmente desde un explorador web o en Teams en cualquier dispositivo. Los recordatorios de correo electrónico automatizados ayudan a reducir las ausencias y a mejorar la participación de los clientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

Con Bookings, obtendrá una experiencia adaptada a su sector. Estos son algunos ejemplos de cómo puede usarlo en su organización:

|Industria | Ejemplos |
|---------|---------|
|Servicios financieros    |  Citas virtuales para ventas y servicios remotos<br/>Programe y administre citas para administradores de relaciones bancarias, asesores financieros y ajustadores de reclamaciones, solo por nombrar algunos, para atender a sus clientes con mayor eficiencia y comodidad.  |
|Venta minorista   | Accesorios y consultas virtuales <br/>Programe y administre citas para que sus asociados de ventas, expertos en productos y consultores de diseño realicen conexiones virtuales y consultas con los clientes.   |
|Salud   |  Citas virtuales para la atención al paciente <br/>Programe y administre citas para que los miembros del equipo de atención médica se reúnan con pacientes u otros proveedores de atención sanitaria para hablar sobre la atención médica.   |

En este artículo se proporciona información general sobre cómo programar, administrar y llevar a cabo citas virtuales mediante la aplicación Bookings en Teams.

## <a name="before-you-get-started"></a>Antes de empezar

Si es administrador, consulte [Administrar la aplicación Bookings en Teams](/microsoftteams/bookings-app-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json) para obtener información sobre los requisitos previos para usar la aplicación Bookings en Teams, cómo controlar el acceso a Bookings en su organización y la configuración recomendada de directivas y administradores.

Recuerde que solo los programadores de la organización necesitan tener instalada la aplicación Bookings en Teams. El personal que realiza o participa en citas virtuales no necesita la aplicación. Se unen a citas desde su calendario de Teams o Outlook, o bien usando el vínculo para la reunión en su correo electrónico de confirmación de reserva.

## <a name="set-up-a-new-booking-calendar"></a>Configurar un nuevo calendario de reservas

### <a name="create-the-booking-calendar"></a>Creación del calendario de reservas

En Teams, vaya a **Bookings** > **Empezar** y seleccione **Nuevo calendario de reservas**. Complete el formulario y asegúrese de elegir el tipo de negocio correspondiente para su organización.

:::image type="content" source="media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Captura de pantalla de la nueva pantalla del calendario de reservas que muestra los tipos de negocio":::

Si es una organización más grande, considere la posibilidad de crear más de un calendario de reservas si desea que los asistentes reciban un correo electrónico de reserva de un departamento específico en lugar de su organización general.
Para más información, consulte [Creación de un calendario de Bookings](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Si esta no es la primera vez que usa la aplicación Bookings o si desea trabajar en un calendario de reservas existente, seleccione la flecha desplegable situada junto al nombre de la organización en Bookings y, a continuación, elija **Calendario de reservas existente**. Desde aquí puede buscar el que quiera.

### <a name="add-staff"></a>Agregar personal

En el calendario de reservas, vaya a **Más opciones** (...) > **Configuración** y, a continuación, seleccione **Personal**. Agregue miembros del personal y asigne un rol a cada persona que agregue. Puede agregar hasta a 100 miembros del personal a un calendario de reservas.

La aplicación Bookings se integra con Outlook. Después de agregar personal, podrá ver la disponibilidad del calendario y programar las reservas para ellos. Para obtener más información, consulte [Agregar personal y ver un calendario de Bookings](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Crear tipos de cita

Cree tipos de citas específicos para representar los servicios ofrecidos por su organización y para adaptar la experiencia de reserva. A continuación, los programadores pueden usar el tipo de cita para programar una cita.

En el calendario de reserva, vaya a **Más opciones** (...) > **Configuración**, seleccione **Tipos de cita** y, a continuación, seleccione **Agregar tipo de cita**. Escriba un nombre&mdash;por ejemplo, Apertura de cuenta, Renovación de receta, Consulta de préstamos, Preparación de impuestos&mdash;y cualquier otra información y configuración que desee.

La información que agregue se incluye en la confirmación por correo electrónico que se envía a los asistentes cada vez que se reserva este tipo de cita. Puede establecer recordatorios de correo electrónico y otras opciones, como si los asistentes pueden [unirse desde un explorador de escritorio o móvil](browser-join.md) sin tener que descargar Teams.

Si es administrador de Bookings, puede vincular hasta cuatro formularios para que los asistentes rellenen cada vez que se reserve este tipo de cita. Por ejemplo, puede necesitar que los asistentes completen un formulario de registro antes de unirse a una cita. Para vincular un formulario, elija **Vincular un formulario**. Escriba la dirección URL del formulario y, a continuación, elija **Vincular**. (Si es la primera vez que vincula un formulario, se le pedirá que cree un grupo de Microsoft 365 para almacenar formularios. Elija **Crear grupo** para crear el grupo. Solo tiene que realizar este procedimiento una vez para el calendario de reservas.)

Al trabajar con formularios, tenga en cuenta lo siguiente:

- Para realizar cambios en un formulario que ya está vinculado a un tipo de cita, seleccione el formulario en el tipo de cita o desde dentro del grupo de Microsoft 365 en [https://forms.office.com](https://forms.office.com).
- La carga de archivos en formularios que contienen una [pregunta de carga de archivos](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) se admite cuando todos los asistentes son de la misma organización.

Cuando un programador usa el tipo de cita para programar una cita, puede optar por incluir el formulario, quitarlo o agregar cualquier otro formulario vinculado al tipo de cita. Los asistentes deben rellenar el formulario antes de unirse a la cita.

> [!NOTE]
> Si es un proveedor de atención sanitaria, usted debe descargar, copiar y/o anotar directamente en los registros médicos cualquier información proporcionada por usted o por los pacientes en Teams (incluida la aplicación Forms, la aplicación Bookings, las grabaciones de reuniones si las habilita o cualquier otro servicio de citas virtuales de Teams) que sea necesaria para su continuidad o retención. Este servicio no mantiene registros médicos legales ni un conjunto de registros designado.

Para obtener más información, consulte [Creación de un tipo de cita](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-an-appointment"></a>Programar una cita

En el calendario de reservas, seleccione **Nueva reserva**. Seleccione un tipo de cita y rellene la información pertinente.

Esto incluye información de contacto de los asistentes, el miembro del personal que proporcionará el servicio, notas internas que solo el personal puede ver, recordatorios por correo electrónico y si el asistente puede unirse desde un explorador móvil. Si un formulario está vinculado al tipo de cita, puede optar por incluirlo, quitarlo o agregar cualquier otro formulario vinculado.

La confirmación por correo electrónico enviada al asistente incluye el vínculo de reunión y los datos adjuntos para que puedan agregar la cita virtual a su calendario. El personal también recibe una confirmación por correo electrónico y una invitación a la reunión. Si se incluyó un formulario en la cita, los administradores y programadores de Bookings pueden ver si el asistente completó el formulario antes de la cita y pueden ver la respuesta del asistente.

Para obtener más información, consulte [Programar una reserva en la aplicación Reservas de Teams](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-an-appointment"></a>Realizar una cita

En el calendario de Teams o de Outlook, vaya a la reserva y seleccione **Unirse** o el vínculo de reunión de Teams. Compruebe la configuración de audio y vídeo y, a continuación, seleccione **Unirse ahora**. Para obtener más información, consulte [Dirigir una cita de Bookings](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>Supervise las citas y obtenga de actualizaciones de estado en tiempo real

La [vista de cola](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) de Bookings proporciona a su personal un panel para supervisar todas las citas virtuales del día con actualizaciones en tiempo real. Para ver la cola, vaya a la pestaña **Cola** de Bookings.

:::image type="content" source="media/bookings-virtual-visits-queue.png" alt-text="Captura de pantalla de la vista de cola en la aplicación Bookings en Teams" lightbox="media/bookings-virtual-visits-queue.png":::

Los programadores pueden agregar una nueva reserva desde la cola, así como ver los detalles pertinentes de la cita y ver los estados de las citas durante todo el día. Cuando un paciente se une a la sala de espera, el estado cambia y su tiempo de espera se muestra y se realiza un seguimiento. La vista se actualiza automáticamente con actualizaciones codificadas por colores para que los cambios se puedan identificar fácilmente.

El personal puede incluso unirse y administrar citas directamente desde la cola.

> [!NOTE]
> Actualmente, la aplicación Bookings admite la incorporación de hasta 100 empleados por calendario de reserva. Si usó Graph API para configurar y agregar personal a un calendario de reserva, es posible que este límite no se aplique. En este escenario, la pestaña **Cola** no podrá mostrar contenido para calendarios con más de 100 empleados. Para una experiencia óptima, te recomendamos que no agregues más de 100 empleados a un calendario de reservas. Estamos trabajando para resolver esta limitación en futuras versiones.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Funcionalidades adicionales con la aplicación web Bookings

La aplicación web bookings le ofrece funcionalidades adicionales. Por ejemplo, puede publicar una página de reserva en línea de autoservicio en la que las personas pueden programar citas con su personal. Para acceder a la aplicación web de Bookings, vaya a **Más opciones** (...) > **Abrir aplicación web de Bookings**.

Para más información, vea [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-appointments-usage"></a>Obtener información sobre el uso de citas virtuales

El [Informe de uso de visitas virtuales](virtual-visits-usage-report.md) en el centro de administración de Microsoft Teams proporciona a los administradores información general sobre la actividad de citas virtuales de Teams en su organización. El informe muestra análisis detallados de citas virtuales, incluidas las citas de Bookings.

Puede consultar métricas clave como el tiempo de espera en la sala de espera y la duración de las citas. Use esta información para conocer las tendencias de uso y así poder optimizar las citas virtuales para obtener mejores resultados empresariales.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la experiencia de unión para las citas virtuales de Teams en los exploradores](browser-join.md)

- [Informe de uso de consultas virtuales de Teams](virtual-visits-usage-report.md)

- [Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)

- [Aplicación de Bookings en la documentación de ayuda de Teams](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
