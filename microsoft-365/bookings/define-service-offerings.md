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
description: Instrucciones para especificar la información de ofertas de servicio, incluido el nombre del servicio, la descripción, la ubicación, la duración y los precios. También puede etiquetar a los empleados cualificados para proporcionar el servicio.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962542"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definir las ofertas de servicio en Bookings

Al definir las ofertas de servicio en Microsoft Bookings, establece un nombre de servicio, una descripción, una ubicación (elija si desea reunirse en persona o tener una reunión en línea), la duración, los avisos predeterminados a los clientes y el personal, las notas internas sobre el servicio y los precios. También puede etiquetar a los empleados cualificados para proporcionar el servicio. A continuación, cuando los clientes vienen al sitio web de su empresa para reservar una cita, pueden ver exactamente qué tipos de citas están disponibles, elegir la persona a la que desean proporcionar el servicio y cuánto costará su servicio.

También puede agregar información y direcciones URL personalizadas a la confirmación de correo electrónico y los avisos que envíe cuando alguien reserve un servicio a través de la página de reserva.

## <a name="create-the-service-details"></a>Crear los detalles del servicio

1. Vaya a la [página Administrar servicios](https://outlook.office.com/bookings/services) y seleccione Agregar un **servicio.**

2. **Nombre del** servicio: escriba el nombre de su servicio. Este es el nombre que aparecerá en el menú desplegable de la página Calendario. Este nombre también aparecerá cuando alguien agrega manualmente una cita en la página Calendario y aparecerá como un icono en la página Autoservicio.

3. **Descripción:** la descripción que escriba es la que aparecerá cuando un usuario haga clic en el icono de información de la página De autoservicio.

4. **Ubicación predeterminada:** esta ubicación es lo que se mostrará en los correos electrónicos de confirmación y aviso para el personal y los clientes, y se mostrará en el evento de calendario creado para la reserva.

5. **Agregar reunión en** línea: esta configuración habilita o deshabilita las reuniones en línea para cada cita, ya sea a través de Teams o Skype, según cuál configure como cliente predeterminado para el miembro del personal.

    - Habilitado:

        - Se agregará un vínculo a una reunión de Teams o Skype, única para la reserva, al evento de calendario en los calendarios del personal y de los clientes, junto con la información de acceso telefónico.
        - El vínculo para unirse a la reunión se agregará a todos los correos electrónicos de confirmación y aviso, como se muestra en el siguiente ejemplo:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Ejemplo de vínculo para unirse a la reunión de Teams en Bookings":::

        > [!NOTE]
        > Las reuniones de Teams se pueden unir a través de la aplicación móvil de Teams, la aplicación de escritorio de Teams, en un explorador web o a través del acceso telefónico. Le recomendamos encarecidamente que habilite Teams como el servicio de reuniones en línea predeterminado para su espacio empresarial, para obtener la mejor experiencia reservando citas virtuales.

    - Deshabilitado:
        - Las citas no contendrán una opción de reunión y no  se mostrarán todos los campos relacionados con la reunión que aparecen cuando se habilita Agregar reunión en línea.

6. **Duración predeterminada:** es el tiempo durante el que se reservarán todas las reuniones. La hora se bloquea a partir de la hora de inicio, que se selecciona durante la reserva. Se bloqueará la hora completa de la cita en los calendarios del personal.

7. **Tiempo de búfer que el** cliente no puede reservar: habilitar esta configuración permite agregar tiempo adicional al calendario del personal cada vez que se reserva una cita.

    La hora se bloqueará en el calendario del personal y afectará a la información de disponibilidad. Esto significa que si una cita finaliza a las 3:00 p.m. y se han agregado 10 minutos de tiempo de búfer al final de la reunión, el calendario del personal se mostrará como ocupado y no se puede reservar hasta las 3:10 p.m. Esto puede ser útil si el personal necesita tiempo antes de una reunión para prepararse, como un médico que revisa el gráfico de un paciente o un asesor financiero que prepara la información de cuenta relevante. También puede ser útil después de una reunión, como cuando alguien necesita tiempo para desplazarse a otra ubicación.

8. **Permitir que** el cliente administre su reserva: esta configuración determina si el cliente puede modificar o cancelar su reserva, siempre que se haya reservado a través de la pestaña Calendario en la aplicación web de Bookings.

    - Habilitado:

        El **botón Administrar reserva** aparece en el correo electrónico de confirmación del cliente. Cuando el cliente selecciona este botón, aparecen tres opciones:
        - **Reprogramar** La selección de esta opción lleva al usuario a una página de Self-Service específica del servicio, donde puede seleccionar una nueva hora y/o fecha para el mismo servicio y el mismo miembro del personal de la reserva original. Tenga en cuenta que aunque el miembro del personal original se adjunta a la reserva reprogramada de forma predeterminada, el usuario también tiene la opción de cambiar al miembro del personal.
        - **Cancelar reserva** Esto cancela la reserva y la quita del calendario del personal.
        - **Nueva reserva** Esta opción lleva al usuario a la Self-Service con todos los servicios y el personal enumerados, para programar una nueva reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="El botón Administrar Bookings en Bookings":::

        Solo te recomendamos dejar esta configuración habilitada si estás cómodo con los clientes que acceden a la Self-Service web.

    - Deshabilitado:

        El usuario no podrá reprogramar o cancelar su reserva cuando reserve a través de la pestaña Calendario en la aplicación web de Bookings. Sin embargo, al reservar a través Self-Service página,  los clientes seguirán teniendo el botón Administrar reserva y todas sus opciones, incluso cuando esta configuración esté deshabilitada.

        Te recomendamos deshabilitar esta configuración si quieres limitar el acceso a la Self-Service página. Además, se recomienda agregar texto a los correos electrónicos de confirmación y aviso que indique a los clientes cómo realizar cambios en su reserva a través de otros medios, como llamar a la oficina o enviar un correo electrónico al servicio de ayuda.

9. **Número máximo de asistentes por evento** Esta configuración le permite crear servicios que requieren la capacidad de varias personas para reservar la misma hora de cita y el mismo personal (por ejemplo, una clase de ejercicio físico). La franja horaria de cita para el servicio, el personal y el tiempo seleccionados estarán disponibles para reservar hasta que se alcance el número máximo de asistentes, especificado por usted. La capacidad y los asistentes de las citas actuales se pueden ver en la pestaña Calendario de la aplicación web de Bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Ejemplo de configuración del número máximo de asistentes en Bookings":::

10. **Precio predeterminado**  Este es el precio que se mostrará en la Self-Service página. Si **el precio no establecido** está seleccionado, no aparecerá ningún precio o referencia al costo o al precio.

11. **Notas** Este campo aparece en el evento de reserva para el personal reservado, así como en el evento que aparece en la pestaña Calendario en la aplicación web de Bookings.

12. **Campos personalizados** Esta sección permite agregar o quitar preguntas si el cliente necesita responder a alguna para poder realizar la reserva correctamente.

    - El correo electrónico del cliente, el número de teléfono, la dirección y las notas son campos no extraíbles, pero puede hacerlos opcionales anulando la selección de **Obligatorio** junto a cada campo.

    - Puede agregar una pregunta de opción múltiple o de respuesta de texto **seleccionando Agregar una pregunta.**

        Los campos personalizados pueden ser útiles al recopilar información necesaria cada vez que se reserva la cita específica. Algunos ejemplos son el proveedor de seguros antes de una visita de visita, el tipo de préstamo para consultas de préstamo, el estudio principal de asesoramiento académico o el id. de solicitante para las entrevistas de candidatos.

13. **Avisos y confirmaciones** Ambos tipos de correos electrónicos se envían a clientes, miembros del personal o ambos, en un período de tiempo especificado antes de la cita. Se pueden crear varios mensajes para cada cita, según sus preferencias.

    - Los correos electrónicos de confirmación y aviso predeterminados incluyen información básica sobre la cita, como el nombre del cliente o cliente, el nombre del miembro del personal, el servicio o la cita reservada y la hora de la cita. Para las reuniones en línea, también se incluirá un vínculo para unirse. También se puede incluir la capacidad de administrar la reserva, si esta configuración está habilitada (como se describió anteriormente en el paso 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Un correo electrónico de confirmación de Bookings":::

    - Opcionalmente, puedes incluir cualquier texto adicional que quieras aquí, como información sobre la reprogramación o lo que los clientes deben traer para la cita. A continuación se muestra un ejemplo de texto personalizado agregado al correo electrónico de confirmación original, que se muestra en el **campo Información adicional** para confirmación de correo electrónico:

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Información adicional en un correo electrónico de Bookings":::

14. **Habilitar las notificaciones de mensajes de texto para el cliente** Si se selecciona, los mensajes SMS se envían al cliente, pero solo si optan por participar.

    - Cuadro de suscripción en la página de reserva manual Self-Service usuario:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="El cuadro de opción en Bookings":::

    - Las notificaciones de mensajes de texto tendrán un aspecto como el siguiente (tenga en cuenta que actualmente las notificaciones SMS solo están disponibles en Norteamérica):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Una notificación de texto de Bookings":::

15. **Opciones de publicación** Elija si desea que este servicio aparezca como se puede reservar en la página Self-Service o si desea que el servicio se pueda reservar solo en la pestaña Calendario dentro de la aplicación web de Bookings.

16. **Directiva de programación** Esta configuración determina cómo se ven las horas de cita y el período de tiempo en el que se pueden realizar o cancelar reservas.

17. **Notificaciones por correo electrónico** Establece cuándo se envían mensajes de correo electrónico al personal de la organización y a clientes o clientes.

18. **Personal** Al activar esta casilla, los clientes pueden elegir un miembro del personal específico para su cita.

    - Habilitado:

        Los clientes pueden elegir entre todo el personal asignado a la cita al reservar en Self-Service página. Al seleccionar la opción **Cualquiera,** Bookings elegirá un miembro del personal disponible aleatoriamente para asignar a la cita.

    - Deshabilitado:

        Los clientes que reservan a través Self-Service página pueden seleccionar un servicio y una hora y fecha. El personal disponible se reservará aleatoriamente. Tenga en cuenta que se puede seleccionar un personal específico cuando se reserva a través de la pestaña Calendario en la aplicación web de Bookings.

19. **Disponibilidad** Las siguientes opciones determinan cuándo se puede reservar el servicio:

    - **Se puede reservar cuando el personal es gratuito** El servicio mantiene la disponibilidad en función de cuándo el personal esté libre dentro del horario comercial, sin restricciones de tiempo adicional.

    - **Horas personalizadas (periódicas semanalmente)** El servicio tiene una capa adicional de disponibilidad que se puede restringir aún más (además de restringir el horario comercial o el horario del personal). Use esta opción cuando solo se pueda proporcionar o realizar el servicio en un momento específico.

    - **Establecer disponibilidad diferente para un intervalo de fechas** Esta configuración afecta a la disponibilidad en un momento específico en el tiempo, en lugar de una base periódica. Por ejemplo, esto se puede usar cuando una máquina que se necesita para el servicio está temporalmente en mantenimiento y no está disponible, o cuando una organización está cerrada por vacaciones.

20. **Asignar personal** Seleccione el personal (siempre que haya agregado miembros del personal a la pestaña Personal) que se podrán reservar para ese servicio específico. Si no se selecciona ningún personal individual, se asignará todo el personal al servicio.