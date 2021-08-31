---
title: Definir las ofertas de servicio en Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instrucciones para especificar información sobre ofertas de servicio, incluidos el nombre del servicio, la descripción, la ubicación, la duración y los precios. También puede etiquetar a los empleados que están cualificados para proporcionar el servicio.
ms.openlocfilehash: 5b9720492429a6a46be8f2701315ccd5b92e1bf6
ms.sourcegitcommit: c41e3f48451e2d7b45901faee21b1e1d19a16688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2021
ms.locfileid: "58823882"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definir las ofertas de servicio en Bookings

Al definir las ofertas de servicio en Microsoft Bookings, establece un nombre de servicio, una descripción, una ubicación (elija si desea reunirse en persona o tener una reunión en línea), la duración, los avisos predeterminados a los clientes y el personal, las notas internas sobre el servicio y los precios. También puede etiquetar a los empleados que están cualificados para proporcionar el servicio. A continuación, cuando los clientes se acercan a su sitio web empresarial para reservar una cita, pueden ver exactamente qué tipos de citas están disponibles, elegir la persona que desean proporcionar el servicio y cuánto costará su servicio.

También puede agregar información personalizada y direcciones URL a la confirmación de correo electrónico y los avisos que envíe cuando alguien reserve un servicio a través de la página de reserva.

## <a name="create-the-service-details"></a>Crear los detalles del servicio

1. En Microsoft 365, seleccione el iniciador de aplicaciones y, a continuación, **seleccione Bookings**.

2. Vaya a **Configuración**  ->  [página Administrar servicios](https://outlook.office.com/bookings/settings/services) y seleccione Agregar nuevo **servicio**.

3. En la **página Detalles básicos,** agregue las selecciones.

**Nombre del servicio:** escriba el nombre del servicio. Este es el nombre que aparecerá en el menú desplegable de la página Calendario. Este nombre también aparecerá cuando alguien agrega manualmente una cita en la página Calendario y aparecerá como un icono en la página Autoservicio.

**Descripción:** la descripción que escriba es la que aparecerá cuando un usuario haga clic en el icono de información en la página Autoservicio.

**Ubicación predeterminada:** esta ubicación es la que se mostrará en los correos electrónicos de confirmación y aviso para el personal y los clientes, y se mostrará en el evento de calendario creado para la reserva.

**Agregar** reunión en línea: esta configuración habilita o deshabilita las reuniones en línea para cada cita, ya sea a través de Teams o Skype, según cuál configure como el cliente predeterminado para el miembro del personal.

    - Habilitado:

        - Un vínculo a una reunión de Teams o Skype, única para la reserva, se agregará al evento de calendario en los calendarios del personal y de los clientes, junto con la información de acceso telefónico.
        - El vínculo para unirse a la reunión se agregará a todos los correos electrónicos de confirmación y aviso, como se muestra en el siguiente ejemplo:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Ejemplo de vínculo para unirse Teams reunión en Bookings.":::

        > [!NOTE]
        > Teams reuniones pueden unirse a través de la aplicación móvil de Teams, la aplicación de escritorio de Teams, en un explorador web o a través del acceso telefónico telefónico. Recomendamos encarecidamente habilitar Teams como el servicio de reuniones en línea predeterminado para su inquilino, para obtener la mejor experiencia al reservar citas virtuales.

    - Deshabilitado:
        - Las citas no contendrán una opción de reunión y no  se mostrarán todos los campos relacionados con la reunión que aparecen cuando se habilita Agregar reunión en línea.

**Duración:** este es el tiempo durante el que se reservarán todas las reuniones. La hora se bloquea a partir de la hora de inicio, que se selecciona durante la reserva. La hora completa de la cita se bloqueará en los calendarios del personal.

**Tiempo de búfer:** la habilitación de esta configuración permite agregar tiempo adicional al calendario del personal cada vez que se reserva una cita.

    The time will be blocked on the staff’s calendar and impact free/busy information. This means if an appointment ends at 3:00 pm and 10 minutes of buffer time has been added to the end of the meeting, the staff’s calendar will show as busy and non-bookable until 3:10pm. This can be useful if your staff needs time before a meeting to prepare, such as a doctor reviewing a patient’s chart, or a financial advisor preparing relevant account information. It can also be useful after a meeting, such as when someone needs time to travel to another location.

**Precio no establecido**  Seleccione las opciones de precio que se mostrarán en la Self-Service página. Si **el precio no establecido** está seleccionado, no aparecerá ningún precio ni referencia al costo o al precio.

**Notas** Este campo aparece en el evento de reserva para el personal reservado, así como en el evento que aparece en la pestaña Calendario de la aplicación web bookings.

**Máximo de asistentes por evento** Esta configuración le permite crear servicios que requieren la capacidad de varias personas para reservar la misma hora de cita y el mismo personal (como una clase de fitness). La franja horaria de cita para el servicio, el personal y la hora seleccionados estarán disponibles para reservar hasta que se haya alcanzado el número máximo de asistentes, especificado por usted. La capacidad y los asistentes a citas actuales se pueden ver en la pestaña Calendario de la aplicación web de Bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Example of setting maximum attendees in Bookings":::

**Permitir que** el cliente administre su reserva: esta configuración determina si el cliente puede modificar o cancelar su reserva, siempre que se haya reservado a través de la pestaña Calendario de la aplicación web de Bookings.

    - Habilitado:

        El **botón Administrar reserva** aparece en el correo electrónico de confirmación del cliente. Cuando el cliente selecciona este botón, aparecen tres opciones:
        - **Reschedule** Al seleccionar esta opción, el usuario llega a una página de Self-Service específica del servicio, donde puede seleccionar una nueva hora o fecha para el mismo servicio y el mismo miembro del personal de la reserva original. Tenga en cuenta que, aunque el miembro del personal original está unido a la reserva reprogramada de forma predeterminada, el usuario también tiene la opción de cambiar el miembro del personal.
        - **Cancelar reserva** Esto cancela la reserva y la quita del calendario del personal.
        - **Nueva reserva** Esta opción lleva al usuario a la Self-Service con todos los servicios y el personal enumerados, para programar una nueva reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="El botón Administrar reservas en Bookings.":::

        Solo se recomienda dejar esta configuración habilitada si se siente cómodo con los clientes que acceden a la Self-Service web.

    - Deshabilitado:

        El usuario no podrá reprogramar o cancelar su reserva cuando reserve a través de la pestaña Calendario de la aplicación web de Bookings. Sin embargo, al reservar en la Self-Service, los  clientes seguirán teniendo el botón Administrar reserva y todas sus opciones, incluso cuando esta configuración esté deshabilitada.

        Se recomienda deshabilitar esta configuración si desea limitar el acceso a la página Self-Service usuario. Además, se recomienda agregar texto a los correos electrónicos de confirmación y aviso que indiquen a los clientes cómo realizar cambios en su reserva a través de otros medios, como llamar a la oficina o enviar un correo electrónico al servicio de ayuda.

4. En la **página Opciones de** disponibilidad, puede ver  las opciones que ha seleccionado en la página De reserva para la directiva de programación y la disponibilidad de su personal. Para obtener más información, vea [Set your scheduling policies](set-scheduling-policies.md).

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Ejemplo de configuración del número máximo de asistentes en Bookings.":::

10. **Precio predeterminado**  Este es el precio que se mostrará en la Self-Service página. Si **el precio no establecido** está seleccionado, no aparecerá ningún precio ni referencia al costo o al precio.

11. **Notas** Este campo aparece en el evento de reserva para el personal reservado, así como en el evento que aparece en la pestaña Calendario de la aplicación web bookings.

6. **Los campos personalizados** pueden ser útiles al recopilar información que se necesita cada vez que se reserva la cita específica. Algunos ejemplos incluyen el proveedor de seguros antes de una visita a una clínica, el tipo de préstamo para consultas de préstamo, el principal de estudio para asesoramiento académico o el identificador de solicitante para las entrevistas de candidato. Estos campos aparecerán en la página Booking cuando los clientes reserven citas con usted y su personal.

    - El correo electrónico del cliente, el número de teléfono, la dirección y las notas son campos no extraíbles, pero puede hacerlos opcionales anulando la selección obligatorio **junto** a cada campo.

7. En la **página Avisos y** confirmaciones, puede configurar avisos y notificaciones que envíe. Los avisos y notificaciones se envían a clientes, miembros del personal o ambos, en un momento especificado antes de la cita. Se pueden crear varios mensajes para cada cita, según su preferencia.

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="A confirmation email from Bookings.":::

    - Puede incluir cualquier texto adicional que quiera aquí, como información sobre la reprogramación o lo que los clientes deben traer para la cita. A continuación se muestra un ejemplo de texto personalizado agregado al correo electrónico de confirmación original, que se muestra en el **campo Información adicional para** confirmación de correo electrónico:

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Información adicional en un correo electrónico de Bookings.":::

8. **Habilitar notificaciones de mensajes de texto para el cliente** Si se selecciona, los mensajes SMS se envían al cliente, pero solo si optan por participar.

    - Cuadro de suscripción en la página manual de reserva y Self-Service:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="El cuadro de suscripción en Bookings.":::

    - Las notificaciones de mensajes de texto tendrán un aspecto parecido al siguiente (tenga en cuenta que las notificaciones SMS solo están disponibles actualmente en Norteamérica):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Una notificación de texto de Bookings.":::

9. De **forma predeterminada, las** opciones de programación predeterminadas están en. Desactiva la alternancia si quieres personalizar la forma en que los clientes reservan a un miembro del personal en particular.

10. **Opciones de publicación** Elige si este servicio aparece como reservable en la página Self-Service o para que el servicio se pueda reservar solo en la pestaña Calendario de la aplicación web de Bookings.
