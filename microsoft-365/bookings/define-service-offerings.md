---
title: Definición de las ofertas de servicio de Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instrucciones para especificar información sobre ofertas de servicio, incluidos el nombre del servicio, la descripción, la ubicación, la duración y los precios. También puede etiquetar a los empleados calificados para proporcionar el servicio.
ms.openlocfilehash: 2daae2139e3d2d4107f4aaed1b94ca655877000a
ms.sourcegitcommit: af2b570e76e074bbef98b665b5f9a731350eda58
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2022
ms.locfileid: "66185091"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definición de las ofertas de servicio en Bookings

Al definir las ofertas de servicio en Microsoft Bookings, establece un nombre de servicio, una descripción, una ubicación (elija si desea reunirse en persona o tener una reunión en línea), la duración, los avisos predeterminados para los clientes y el personal, las notas internas sobre el servicio y los precios. También puede etiquetar a los empleados calificados para proporcionar el servicio. A continuación, cuando los clientes llegan a su sitio web empresarial para reservar una cita, pueden ver exactamente qué tipos de citas están disponibles, elegir la persona a la que quieren proporcionar el servicio y cuánto costará su servicio.

También puede agregar información personalizada y direcciones URL a la confirmación por correo electrónico y recordatorios que envíe cuando alguien reserve un servicio a través de su página de reserva.

## <a name="watch-create-a-new-service"></a>Inspección: Creación de un nuevo servicio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuKXH]

## <a name="steps"></a>Pasos

1. En Microsoft 365, seleccione el iniciador de aplicaciones y, a continuación, seleccione **Reservas**.

2. Vaya a **Servicios de calendario** > **y seleccione** **Agregar nuevo servicio**.

3. En la página **Detalles básicos** , agregue las selecciones.

   **Nombre del** servicio: escriba el nombre del servicio. Este es el nombre que aparecerá en el menú desplegable de la página Calendario. Este nombre también aparecerá cuando alguien agregue manualmente una cita en la página Calendario y aparecerá como un icono en la página Autoservicio.

   **Descripción**: la descripción que escriba es la que aparecerá cuando un usuario haga clic en el icono de información de la página Autoservicio.

   **Ubicación predeterminada**: esta ubicación es la que se mostrará en los correos electrónicos de confirmación y recordatorio para el personal y los clientes, y se mostrará en el evento de calendario creado para la reserva.

   **Agregar reunión en línea**: esta configuración habilita o deshabilita las reuniones en línea para cada cita, ya sea a través de Teams o Skype, dependiendo de cuál configure como cliente predeterminado para el miembro del personal.

   - Habilitado:
     - Se agregará un vínculo a una reunión de Teams o Skype, única para la reserva, al evento de calendario en los calendarios del personal y de los clientes, junto con información de acceso telefónico local.
     - El vínculo para unirse a la reunión se agregará a todos los correos electrónicos de confirmación y recordatorio, como se muestra en el ejemplo siguiente:

       :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Ejemplo de vínculo para unirse a Teams reunión en Bookings.":::

       > [!NOTE]
       > Teams reuniones se pueden unir a través de la aplicación móvil Teams, la aplicación de escritorio Teams, en un explorador web o mediante el acceso telefónico local. Se recomienda encarecidamente habilitar Teams como el servicio de reuniones en línea predeterminado para su inquilino, para obtener la mejor experiencia en la reserva de citas virtuales.

   - Deshabilitado:
     - Citas no contendrá una opción de reunión y no se mostrarán todos los campos relacionados con la reunión que aparecen cuando se habilita **Agregar reunión en línea**.

   **Duración**: es el tiempo durante el que se reservarán todas las reuniones. La hora se bloquea a partir de la hora de inicio, que se selecciona durante la reserva. La hora de la cita completa se bloqueará en los calendarios del personal.

   **Tiempo de búfer**: habilitar esta configuración permite agregar tiempo adicional al calendario del personal cada vez que se reserva una cita.

   El tiempo se bloqueará en el calendario del personal y afectará a la información de disponibilidad. Esto significa que si una cita termina a las 3:00 p.m. y se han agregado 10 minutos de tiempo de búfer al final de la reunión, el calendario del personal se mostrará como ocupado y no reservable hasta las 3:10 p. m. Esto puede ser útil si su personal necesita tiempo antes de una reunión para prepararse, como un médico que revisa el gráfico de un paciente o un asesor financiero que prepara la información pertinente de la cuenta. También puede ser útil después de una reunión, como cuando alguien necesita tiempo para viajar a otra ubicación.

   **Precio no establecido**: seleccione las opciones de precio que se mostrarán en la página de Self-Service. Si **se selecciona Price not set (Precio no establecido** ), no aparecerá ningún precio o referencia al costo o al precio.

   **Notas**: Este campo aparece en el evento de reserva del personal reservado, así como en el evento que aparece en la pestaña Calendario de la aplicación web Bookings.

   **Número máximo de asistentes por evento**: esta configuración le permite crear servicios que requieren la posibilidad de que varias personas reserven la misma hora de cita y el mismo personal (por ejemplo, una clase de fitness). El espacio de tiempo de cita para el servicio, el personal y el tiempo seleccionados estarán disponibles para reservar hasta que se haya alcanzado el número máximo de asistentes, especificado por usted. La capacidad de cita actual y los asistentes se pueden ver en la pestaña Calendario de la aplicación web Bookings.

   :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Ejemplo de establecimiento del número máximo de asistentes en Bookings":::

   **Permitir que el cliente administre su reserva**: esta configuración determina si el cliente puede modificar o cancelar su reserva, siempre que se haya reservado a través de la pestaña Calendario de la aplicación web Bookings.

   - Habilitado:

     El botón **Administrar reserva** aparece en el correo electrónico de confirmación del cliente. Cuando el cliente selecciona este botón, aparecen tres opciones:

     - **Reprogramar** Al seleccionar esta opción, el usuario llega a una página de Self-Service específica del servicio, donde puede seleccionar una nueva hora o fecha para el mismo servicio y el mismo miembro del personal de la reserva original. Tenga en cuenta que, aunque el miembro del personal original está asociado a la reserva reprogramada de forma predeterminada, el usuario también tiene la opción de cambiar el miembro del personal.
     - **Cancelación de la reserva** Esto cancela la reserva y la quita del calendario del personal.
     - **Nueva reserva** Esta opción lleva al usuario a la página de Self-Service con todos los servicios y el personal enumerados, para programar una nueva reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="El botón Administrar reservas de Bookings.":::

      Solo se recomienda dejar habilitada esta configuración si se siente cómodo con los clientes que acceden a la página de Self-Service.

   - Deshabilitado:

     El usuario no podrá volver a programar o cancelar su reserva cuando realice la reserva a través de la pestaña Calendario de la aplicación web Bookings. Sin embargo, al realizar la reserva a través de la página de Self-Service, los clientes seguirán teniendo el botón **Administrar reserva** y todas sus opciones, incluso cuando esta configuración esté deshabilitada.

     Se recomienda deshabilitar esta configuración si desea limitar el acceso a la página de Self-Service. Además, te sugerimos que agregues texto a tus correos electrónicos de confirmación y recordatorio que indiquen a tus clientes cómo realizar cambios en su reserva a través de otros medios, como llamando a la oficina o enviando un correo electrónico al departamento de soporte técnico.

4. En la página **Opciones de disponibilidad** , puede ver las opciones que ha seleccionado en la **página Reserva** para la directiva de programación y la disponibilidad del personal. Para obtener más información, consulte [Establecer las directivas de programación](set-scheduling-policies.md).

5. **Precio predeterminado**  Este es el precio que se mostrará en la página de Self-Service. Si **se selecciona Price not set (Precio no establecido** ), no aparecerá ningún precio o referencia al costo o al precio.

6. **Notas** Este campo aparece en el evento de reserva del personal reservado, así como en el evento que aparece en la pestaña Calendario de la aplicación web Bookings.

7. **Los campos personalizados** pueden ser útiles al recopilar información necesaria cada vez que se reserva la cita específica. Algunos ejemplos son el proveedor de seguros antes de una visita a la clínica, el tipo de préstamo para consultas de préstamos, el mayor de estudio para asesoramiento académico o el identificador del solicitante para las entrevistas de candidatos. Estos campos aparecerán en la página Reserva cuando los clientes reserven citas con usted y su personal.

   El correo electrónico del cliente, el número de teléfono, la dirección y las notas son campos no extraíbles, pero puede convertirlos en opcionales si anula la selección de **Requerido** junto a cada campo.

8. En la página **Avisos y confirmaciones** , puede configurar avisos y notificaciones que envíe. Los avisos y las notificaciones se envían a los clientes, miembros del personal o ambos, en un momento especificado antes de la cita. Se pueden crear varios mensajes para cada cita, según sus preferencias.

   :::image type="content" source="media/bookings-remind-confirm-2.png" alt-text="Un correo electrónico de confirmación de Bookings.":::

   Puede incluir cualquier texto adicional que desee aquí, como información sobre la reprogramación o lo que los clientes deben traer para la cita. A continuación se muestra un ejemplo de texto personalizado agregado al correo electrónico de confirmación original, que se muestra en el campo **Información adicional para confirmación por correo electrónico** :

   :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Información adicional en un correo electrónico de Bookings.":::

9. **Habilitación de notificaciones de mensajes de texto para el cliente** Si se selecciona, SMS mensajes se envían al cliente, pero solo si optan por participar.

   - Apartado de participación en la reserva manual y Self-Service Página:

     :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="El apartado de participación de Bookings.":::

   - Las notificaciones de mensajes de texto tendrán un aspecto similar al siguiente (tenga en cuenta que las notificaciones de SMS solo están disponibles actualmente en Norteamérica):

     :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Una notificación de texto de Bookings.":::

10. Las **opciones de programación predeterminadas** están activadas de forma predeterminada. Desactive el botón de alternancia si desea personalizar cómo los clientes reservan a un miembro del personal determinado.

11. **Opciones de publicación** Elija si desea que este servicio aparezca como reservable en la página de Self-Service o para que el servicio solo se pueda reservar en la pestaña Calendario de la aplicación web Bookings.
