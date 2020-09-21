---
title: Definir las ofertas de servicios en las reservas
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instrucciones para introducir información sobre ofertas de servicio, como el nombre, la descripción, la ubicación, la duración y el precio del servicio. También puede etiquetar a los empleados que están cualificados para proporcionar el servicio.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962542"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definir las ofertas de servicios en las reservas

Al definir las ofertas de servicio en Microsoft Bookings, usted establece, un nombre de servicio, una descripción, una ubicación (elija si desea reunirse en persona o tener una reunión en línea), la duración, los avisos predeterminados a los clientes y el personal, notas internas sobre el servicio y precios. También puede etiquetar a los empleados que están cualificados para proporcionar el servicio. A continuación, cuando los clientes visiten el sitio web de la empresa para reservar una cita, podrán ver exactamente qué tipos de citas están disponibles, elegir la persona que quieren proporcionar el servicio y cuánto costará su servicio.

También puede agregar información personalizada y direcciones URL a la confirmación de correo electrónico y los avisos que envía cuando alguien dirige un servicio a través de la página de reserva.

## <a name="create-the-service-details"></a>Crear los detalles del servicio

1. Vaya a la [Página administrar servicios](https://outlook.office.com/bookings/services) y seleccione **Agregar un servicio**.

2. **Nombre del servicio**: escriba el nombre del servicio. Este es el nombre que aparecerá en el menú desplegable de la página calendario. Este nombre también aparecerá cuando un usuario agregue manualmente una cita en la página del calendario y aparecerá como un icono en la página de autoservicio.

3. **Descripción**: la descripción que escriba es lo que aparecerá cuando un usuario haga clic en el icono de información en la página de autoservicio.

4. **Ubicación predeterminada**: esta ubicación es la que se mostrará en los mensajes de correo electrónico de confirmación y avisos para el personal y los clientes, y se mostrará en el evento de calendario creado para la reserva.

5. **Agregar reunión en línea**: esta configuración habilita o deshabilita las reuniones en línea para cada cita, ya sea mediante Teams o Skype, en función de lo que configure como el cliente predeterminado para el miembro del personal.

    - Preparado

        - Se agregará un vínculo a una reunión de Microsoft Teams o Skype, que es único para la reserva, en el calendario del personal y de los clientes, junto con la información de acceso telefónico.
        - El vínculo para unirse a la reunión se agregará a todos los correos electrónicos de confirmación y aviso, como se muestra en el siguiente ejemplo:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Ejemplo de vínculo para unirse a una reunión de Microsoft Teams en reservas":::

        > [!NOTE]
        > Las reuniones de Microsoft Teams se pueden unir a través de la aplicación móvil de Microsoft Teams, la aplicación de escritorio de Microsoft Teams, un explorador Web o a través del marcado telefónico. Recomendamos encarecidamente habilitar Teams como servicio de reuniones en línea predeterminado para su inquilino, para que la mejor experiencia Reserve citas virtuales.

    - Capacidad
        - Las citas no contendrán una opción de reunión y no se mostrarán todos los campos relacionados con la reunión que aparecen cuando se habilita **Agregar reunión en línea** .

6. **Duración predeterminada**: este es el tiempo que se reservarán todas las reuniones. La hora se bloquea a partir de la hora de inicio, que se selecciona durante la reserva. La hora de la cita completa se bloqueará en los calendarios del personal.

7. **Tiempo de búfer que el cliente no puede reservar**: al habilitar esta opción, se permite agregar más tiempo al calendario del personal cada vez que se reserva una cita.

    El tiempo se bloqueará en el calendario del personal e influye en la información de disponibilidad. Esto significa que si una cita termina a las 3:00 p.m. y se han agregado 10 minutos de tiempo de almacenaje al final de la reunión, el calendario del personal aparecerá como ocupado y no bookable hasta 3:10pm. Esto puede ser útil si su personal necesita tiempo antes de una reunión para prepararse, como un doctor que revisa el gráfico de un paciente o un asesor financiero que prepara la información de cuenta relevante. También puede resultar útil después de una reunión, como cuando alguien necesita tiempo para viajar a otra ubicación.

8. **Permita que el cliente administre su reserva**: esta configuración determina si o notthe el cliente puede modificar o cancelar su reserva, siempre que se haya reservado a través de la pestaña calendario de la aplicación web Bookings.

    - Preparado

        El botón **administrar reserva** aparece en el correo electrónico de confirmación del cliente. Cuando el cliente selecciona este botón, aparecen tres opciones:
        - Volver a **programar** Al seleccionar esta opción, el usuario se coloca en una página de autoservicio específica del servicio, donde puede seleccionar una nueva hora o fecha para el mismo servicio y el mismo miembro del personal de la reserva original. Tenga en cuenta que, aunque el miembro del personal original esté adjunto a la reserva reprogramada de forma predeterminada, el usuario tiene la opción de cambiar también el miembro del personal.
        - **Cancelar reserva** Esto cancela la reserva y la quita del calendario del personal.
        - **Nueva reserva** Esta opción permite al usuario la página de autoservicio con todos los servicios y el personal de la lista, para programar una nueva reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="El botón administrar reservas en reservas":::

        Se recomienda dejar esta configuración habilitada si se siente cómodo con los clientes que obtienen acceso a la página de autoservicio.

    - Capacidad

        El usuario no tendrá capacidad para volver a programar o cancelar su reserva cuando se ponga en la ficha calendario de la aplicación web Bookings. Sin embargo, cuando se realiza la reserva a través de la página de autoservicio, los clientes tendrán el botón **administrar reserva** y todas sus opciones, incluso si esta configuración está deshabilitada.

        Se recomienda deshabilitar esta opción si desea limitar el acceso a la página de autoservicio. Además, se recomienda agregar texto a la confirmación y correos electrónicos recordatorios que indiquen a los clientes cómo realizar cambios en su reserva a través de otros medios, como llamar a la oficina o enviar un correo electrónico al Departamento de soporte técnico.

9. **Nº máximo de asistentes por evento** Esta configuración le permite crear servicios que requieran que varias personas puedan reservar la misma hora de cita y el mismo personal (por ejemplo, una clase física). El intervalo de tiempo de la cita para el servicio, el personal y el tiempo seleccionados estarán disponibles para el libro hasta que se haya alcanzado el número máximo de asistentes especificado por el usuario. La capacidad de la cita actual y los asistentes se pueden ver en la pestaña calendario de la aplicación web Bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Ejemplo de configuración de los asistentes máximos en las reservas":::

10. **Precio predeterminado**  Se trata del precio que se mostrará en la página de autoservicio. Si se selecciona **precio no definido** , no se mostrará ningún precio o referencia al coste o precio.

11. **Notas** Este campo aparece en el evento de reserva para el personal de reserva, así como en el evento que aparece en la ficha calendario en la aplicación web Bookings.

12. **Campos personalizados** En esta sección se pueden agregar o quitar las preguntas en caso de que el cliente deba responder a cualquiera para que se pueda reservar correctamente.

    - El correo electrónico del cliente, el número de teléfono, la dirección y las notas son campos no extraíbles, pero puede hacerlos opcionales Si anula la selección de **obligatorios** junto a cada campo.

    - Puede Agregar una pregunta de varias opciones o respuesta de texto; para ello, seleccione **Agregar una pregunta**.

        Los campos personalizados pueden ser útiles al recopilar información necesaria cada vez que se reserva la cita específica. Algunos ejemplos son: proveedor de seguros antes de una visita de la clínica, tipo de préstamo para consultas de préstamos, mayor estudio para asesoría académica o identificador del candidato para entrevistas de candidato.

13. **Avisos y confirmaciones** Ambos tipos de mensajes de correo electrónico se envían a los clientes, miembros del personal o ambos, en un período de tiempo determinado antes de la cita. Se pueden crear varios mensajes para cada cita, según sus preferencias.

    - La confirmación predeterminada y los correos electrónicos de aviso incluyen información básica sobre la cita, como el nombre de cliente/cliente, el nombre del miembro del personal, el servicio o la cita reservados y la hora de la cita. Para las reuniones en línea, también se incluirá un vínculo para unirse. La capacidad de administrar la reserva también puede incluirse si esta configuración está habilitada (tal y como se ha descrito anteriormente en el paso 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Un correo electrónico de confirmación de las reservas":::

    - Opcionalmente, puede incluir cualquier texto adicional que le guste, como información sobre la nueva programación o lo que los clientes deben traer para la cita. A continuación se muestra un ejemplo de texto personalizado agregado al correo electrónico de confirmación original, que se muestra en el campo **información adicional para la confirmación del correo electrónico** :

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Información adicional en un correo electrónico de reservas":::

14. **Habilitar notificaciones de mensajes de texto para el cliente** Si se selecciona, los mensajes SMS se envían al cliente, pero solo si se optan por ellos.

    - Casilla opcional de la página reservas manuales y autoservicio:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="El cuadro de opción de reservas":::

    - Las notificaciones de mensajes de texto tendrán un aspecto similar al siguiente (tenga en cuenta que las notificaciones de SMS solo están disponibles actualmente en Norteamérica):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Una notificación de texto de las reservas":::

15. **Opciones de publicación** Elija si desea que el servicio aparezca como bookable en la página de autoservicio o para que el servicio se bookable solo en la pestaña calendario dentro de la aplicación web Bookings.

16. **Directiva de programación** Esta configuración determina cómo se ven las horas de las citas y el período de tiempo en el que se pueden realizar o cancelar las reservas.

17. **Notificaciones por correo electrónico** Establece cuándo se envían los correos electrónicos al personal de la organización y a los clientes o clientes.

18. **Personal** Al seleccionar esta casilla, los clientes o clientes pueden elegir un miembro del personal específico para su cita.

    - Preparado

        Los clientes pueden elegir entre todo el personal asignado a la cita cuando se Reserve en la página de Self-Service. La selección de la opción de **cualquier persona** realizará reservas elija un miembro del personal disponible de forma aleatoria para asignar a la cita.

    - Capacidad

        La reserva de clientes a través de la página de autoservicio puede seleccionar un servicio y una fecha y hora. El personal disponible se reservará de forma aleatoria. Tenga en cuenta que el personal específico puede seguir estando seleccionado cuando se lo reserva a través de la pestaña calendario en la aplicación web Bookings.

19. **Disponibilidad** Las siguientes opciones determinan cuándo se puede reservar el servicio:

    - **Bookable cuando el personal está libre** El servicio mantiene la disponibilidad en función de Cuándo el personal está libre de horario comercial, sin restricciones de tiempo adicionales.

    - **Horas personalizadas (periodicidad semanal)** El servicio tiene una capa agregada de disponibilidad que se puede restringir aún más (además de restringir el horario comercial o con el horario del personal). Use esta opción si el servicio solo se puede proporcionar o realizar a una hora específica.

    - **Establecer una disponibilidad diferente para un intervalo de fechas** Esta configuración afecta a la disponibilidad en un momento específico en el tiempo, en lugar de hacerlo de manera recurrente. Por ejemplo, esto podría usarse cuando un equipo necesario para el servicio se está revisando temporalmente y no está disponible, o cuando una organización está cerrada durante un día festivo.

20. **Asignar personal** Seleccione el personal (siempre que haya agregado miembros del personal a la ficha personal) que será bookable para ese servicio específico. La selección de ningún personal individual tendrá como resultado que todo el personal se asigne al servicio.