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
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962542"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definir las ofertas de servicio en Bookings

Al definir las ofertas de servicio en Microsoft Bookings, establece un nombre de servicio, una descripción, una ubicación (elija si desea reunirse en persona o tener una reunión en línea), la duración, los avisos predeterminados a los clientes y el personal, las notas internas sobre el servicio y los precios. También puede etiquetar a los empleados que están cualificados para proporcionar el servicio. A continuación, cuando los clientes se acercan a su sitio web empresarial para reservar una cita, pueden ver exactamente qué tipos de citas están disponibles, elegir la persona que desean proporcionar el servicio y cuánto costará su servicio.

También puede agregar información personalizada y direcciones URL a la confirmación de correo electrónico y los avisos que envíe cuando alguien reserve un servicio a través de la página de reserva.

## <a name="create-the-service-details"></a>Crear los detalles del servicio

1. Vaya a la [página Administrar servicios](https://outlook.office.com/bookings/services) y seleccione Agregar un **servicio**.

2. **Nombre del servicio:** escriba el nombre del servicio. Este es el nombre que aparecerá en el menú desplegable de la página Calendario. Este nombre también aparecerá cuando alguien agrega manualmente una cita en la página Calendario y aparecerá como un icono en la página Autoservicio.

3. **Descripción:** la descripción que escriba es la que aparecerá cuando un usuario haga clic en el icono de información en la página Autoservicio.

4. **Ubicación predeterminada:** esta ubicación es la que se mostrará en los correos electrónicos de confirmación y aviso para el personal y los clientes, y se mostrará en el evento de calendario creado para la reserva.

5. **Agregar** reunión en línea: esta configuración habilita o deshabilita las reuniones en línea para cada cita, ya sea a través de Teams o Skype, según cuál configure como el cliente predeterminado para el miembro del personal.

    - Habilitado:

        - Un vínculo a una reunión de Teams o Skype, única para la reserva, se agregará al evento de calendario en los calendarios del personal y de los clientes, junto con la información de acceso telefónico.
        - El vínculo para unirse a la reunión se agregará a todos los correos electrónicos de confirmación y aviso, como se muestra en el siguiente ejemplo:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Ejemplo de vínculo para unirse Teams reunión en Bookings":::

        > [!NOTE]
        > Teams reuniones pueden unirse a través de la aplicación móvil de Teams, la aplicación de escritorio de Teams, en un explorador web o a través del acceso telefónico telefónico. Recomendamos encarecidamente habilitar Teams como el servicio de reuniones en línea predeterminado para su inquilino, para obtener la mejor experiencia al reservar citas virtuales.

    - Deshabilitado:
        - Las citas no contendrán una opción de reunión y no  se mostrarán todos los campos relacionados con la reunión que aparecen cuando se habilita Agregar reunión en línea.

6. **Duración predeterminada:** este es el tiempo durante el que se reservarán todas las reuniones. La hora se bloquea a partir de la hora de inicio, que se selecciona durante la reserva. La hora completa de la cita se bloqueará en los calendarios del personal.

7. **Tiempo de búfer que el cliente** no puede reservar: habilitar esta configuración permite agregar tiempo adicional al calendario del personal cada vez que se reserva una cita.

    La hora se bloqueará en el calendario del personal y afectará a la información de disponibilidad. Esto significa que si una cita finaliza a las 3:00 p.m. y se han agregado 10 minutos de tiempo de búfer al final de la reunión, el calendario del personal se mostrará como ocupado y no se puede reservar hasta las 3:10 p.m. Esto puede ser útil si el personal necesita tiempo antes de una reunión para prepararse, como un médico que revisa el gráfico de un paciente o un asesor financiero que prepara la información relevante de la cuenta. También puede ser útil después de una reunión, como cuando alguien necesita tiempo para viajar a otra ubicación.

8. **Permitir que** el cliente administre su reserva: esta configuración determina si el cliente puede modificar o cancelar su reserva, siempre que se haya reservado a través de la pestaña Calendario de la aplicación web de Bookings.

    - Habilitado:

        El **botón Administrar reserva** aparece en el correo electrónico de confirmación del cliente. Cuando el cliente selecciona este botón, aparecen tres opciones:
        - **Reschedule** Al seleccionar esta opción, el usuario llega a una página de Self-Service específica del servicio, donde puede seleccionar una nueva hora o fecha para el mismo servicio y el mismo miembro del personal de la reserva original. Tenga en cuenta que, aunque el miembro del personal original está unido a la reserva reprogramada de forma predeterminada, el usuario también tiene la opción de cambiar el miembro del personal.
        - **Cancelar reserva** Esto cancela la reserva y la quita del calendario del personal.
        - **Nueva reserva** Esta opción lleva al usuario a la Self-Service con todos los servicios y el personal enumerados, para programar una nueva reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="El botón Administrar reservas en Bookings":::

        Solo se recomienda dejar esta configuración habilitada si se siente cómodo con los clientes que acceden a la Self-Service web.

    - Deshabilitado:

        El usuario no podrá reprogramar o cancelar su reserva cuando reserve a través de la pestaña Calendario de la aplicación web de Bookings. Sin embargo, al reservar en la Self-Service, los  clientes seguirán teniendo el botón Administrar reserva y todas sus opciones, incluso cuando esta configuración esté deshabilitada.

        Se recomienda deshabilitar esta configuración si desea limitar el acceso a la página Self-Service usuario. Además, se recomienda agregar texto a los correos electrónicos de confirmación y aviso que indiquen a los clientes cómo realizar cambios en su reserva a través de otros medios, como llamar a la oficina o enviar un correo electrónico al servicio de ayuda.

9. **Máximo de asistentes por evento** Esta configuración le permite crear servicios que requieren la capacidad de varias personas para reservar la misma hora de cita y el mismo personal (como una clase de fitness). La franja horaria de cita para el servicio, el personal y la hora seleccionados estarán disponibles para reservar hasta que se haya alcanzado el número máximo de asistentes, especificado por usted. La capacidad y los asistentes a citas actuales se pueden ver en la pestaña Calendario de la aplicación web de Bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Ejemplo de configuración de asistentes máximos en Bookings":::

10. **Precio predeterminado**  Este es el precio que se mostrará en la Self-Service página. Si **el precio no establecido** está seleccionado, no aparecerá ningún precio ni referencia al costo o al precio.

11. **Notas** Este campo aparece en el evento de reserva para el personal reservado, así como en el evento que aparece en la pestaña Calendario de la aplicación web bookings.

12. **Campos personalizados** Esta sección permite agregar o quitar preguntas si el cliente necesita responder a alguna para poder reservar correctamente.

    - El correo electrónico del cliente, el número de teléfono, la dirección y las notas son campos no extraíbles, pero puede hacerlos opcionales anulando la selección obligatorio **junto** a cada campo.

    - Puede agregar una pregunta de opción múltiple o de respuesta de texto **seleccionando Agregar una pregunta**.

        Los campos personalizados pueden ser útiles al recopilar información que se necesita cada vez que se reserva la cita específica. Algunos ejemplos incluyen el proveedor de seguros antes de una visita a una clínica, el tipo de préstamo para consultas de préstamo, el principal de estudio para asesoramiento académico o el identificador de solicitante para las entrevistas de candidato.

13. **Avisos y confirmaciones** Ambos tipos de correos electrónicos se envían a clientes, miembros del personal o ambos, en un período de tiempo especificado antes de la cita. Se pueden crear varios mensajes para cada cita, según su preferencia.

    - Los correos electrónicos de confirmación y aviso predeterminados incluyen información básica sobre la cita, como el nombre del cliente o cliente, el nombre del miembro del personal, el servicio o la cita reservada y la hora de la cita. Para las reuniones en línea, también se incluirá un vínculo para unirse. También se puede incluir la capacidad de administrar la reserva, si esta configuración está habilitada (como se describe anteriormente en el paso 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Un correo electrónico de confirmación de Bookings":::

    - Opcionalmente, puede incluir cualquier texto adicional que quiera aquí, como información sobre la reprogramación o lo que los clientes deben traer para la cita. A continuación se muestra un ejemplo de texto personalizado agregado al correo electrónico de confirmación original, que se muestra en el **campo Información adicional para** confirmación de correo electrónico:

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Información adicional en un correo electrónico de Bookings":::

14. **Habilitar notificaciones de mensajes de texto para el cliente** Si se selecciona, SMS mensajes se envían al cliente, pero solo si optan por participar.

    - Cuadro de suscripción en la página manual de reserva y Self-Service:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="El cuadro de suscripción en Bookings":::

    - Las notificaciones de mensajes de texto tendrán un aspecto parecido al siguiente (tenga en cuenta que SMS notificaciones solo están disponibles actualmente en Norteamérica):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Una notificación de texto de Bookings":::

15. **Opciones de publicación** Elige si este servicio aparece como reservable en la página Self-Service o para que el servicio se pueda reservar solo en la pestaña Calendario de la aplicación web de Bookings.

16. **Directiva de programación** Esta configuración determina cómo se ven las horas de cita y el período de tiempo en el que se pueden realizar o cancelar las reservas.

17. **Notificaciones por correo electrónico** Establece cuándo se envían correos electrónicos al personal de la organización y a clientes o clientes.

18. **Personal** Al seleccionar esta casilla, los clientes pueden elegir un miembro del personal específico para su cita.

    - Habilitado:

        Los clientes pueden elegir entre todo el personal asignado a la cita al reservar en la Self-Service web. Al seleccionar la opción **cualquiera, Bookings** elegirá un miembro del personal disponible aleatoriamente para asignar a la cita.

    - Deshabilitado:

        Los clientes que reserven a Self-Service pueden seleccionar un servicio y una hora y fecha. El personal disponible se reservará al azar. Tenga en cuenta que aún se puede seleccionar personal específico cuando se reserva a través de la pestaña Calendario en la aplicación web de Bookings.

19. **Disponibilidad** Las siguientes opciones determinan cuándo se puede reservar el servicio:

    - **Se puede reservar cuando el personal es gratuito** El servicio mantiene la disponibilidad en función de cuándo el personal es gratuito en el horario laboral, sin restricciones de tiempo adicional.

    - **Horas personalizadas (semanales periódicas)** El servicio tiene una capa adicional de disponibilidad que se puede restringir aún más (además de restringir por horario comercial o con horas de personal). Use esta opción cuando el servicio solo se pueda proporcionar o realizar en un momento específico.

    - **Establecer diferentes disponibilidades para un intervalo de fechas** Esta configuración afecta a la disponibilidad en un punto específico del tiempo, en lugar de una base periódica. Por ejemplo, esto se puede usar cuando se está prestando servicio temporalmente a una máquina necesaria para el servicio o cuando una organización está cerrada durante un día festivo.

20. **Asignar personal** Seleccione el personal (siempre que haya agregado miembros del personal a la pestaña Personal) que se podrá reservar para ese servicio específico. Si no se selecciona ningún personal individual, se asignará todo el personal al servicio.