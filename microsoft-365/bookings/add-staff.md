---
title: Agregar personal a las reservas
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: Use esta página para crear la lista de personal y administrar los detalles de los miembros del personal, como el nombre, el número de teléfono y la dirección de correo electrónico.
ms.openlocfilehash: cfd42eedb6e0bea08cdee1503fc373167996c75b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420182"
---
# <a name="add-staff-to-bookings"></a>Agregar personal a las reservas

La página personal de reservas es donde se crea la lista de personal y se administran los detalles de los miembros del personal, como el nombre, el número de teléfono y la dirección de correo electrónico. A partir de aquí, también puede establecer las horas laborables de cada miembro del personal.

> [!NOTE]
> Las reservas están activadas de forma predeterminada para los clientes con las suscripciones Microsoft 365 Business Standard, Microsoft 365 a3 o Microsoft 365 A5. Las reservas también están disponibles para los clientes que tienen Office 365 Enterprise E3 y Office 365 Enterprise E5, pero están desactivados de forma predeterminada. Para empezar, vea [obtener acceso a Microsoft bookings](get-access.md). Para activar o desactivar las reservas, consulte [activar o desactivar las reservas para su organización](turn-bookings-on-or-off.md).

## <a name="add-staff"></a>Agregar personal

Aunque las reservas son una característica de Microsoft 365, no todos los miembros del personal deben tener una cuenta de Microsoft 365. Todos los miembros del personal deben tener una dirección de correo electrónico válida para que puedan recibir reservas y programar cambios.

Vea este vídeo o siga los pasos que se indican a continuación para agregar a su personal.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. Vaya a la [página Administrar personal](https://outlook.office.com/bookings/staff) y seleccione **Agregar personal** .

2. Seleccione el botón **Agregar personal** .

3. Cuando agregue personal desde dentro de su espacio empresarial, escriba su nombre en el campo **Agregar personas** y selecciónelo cuando aparezca en el menú desplegable. Los demás campos se rellenarán automáticamente.

    Una vez agregado un miembro del personal, puede editar el nombre que aparece en todas las comunicaciones de las reservas seleccionando la **x** junto a su nombre y editando el campo **Agregar personas** . Esto puede ser útil si desea que los miembros del personal tengan un título o nombre específico mostrados para los clientes, como enumerar Marta Saavedra como "Dr. Saavedra, MD".

4. Para agregar personal desde fuera de su espacio empresarial, rellene manualmente su correo electrónico y otra información.

    > [!NOTE]
    > El personal de fuera de su inquilino no podrá compartir información de disponibilidad con reservas.

5. Para cada miembro del personal, seleccione un rol: administrador, visor o invitado.
    - Los **administradores** pueden editar toda la configuración, agregar y quitar personal y crear, editar o eliminar reservas.
    - Los **visores** pueden ver todas las reservas en el calendario, pero no pueden modificarlas ni eliminarlas. Tienen acceso de solo lectura a la configuración.
    - Los **invitados** se pueden asignar a las reservas, pero no pueden abrir el buzón de reserva.

6. Seleccione **notificar a todo el personal por correo electrónico cuando se crea o cambia una reserva asignada a ellos** para habilitar los correos electrónicos del personal. El siguiente es un ejemplo de correo electrónico:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Un correo electrónico de notificación de las reservas":::

7. **Los eventos Select del calendario de Office 365 afectan** a la disponibilidad si desea que la información de disponibilidad de los calendarios de los miembros del personal afecte a la disponibilidad de los servicios de reservas mediante reservas.

    Por ejemplo, si un miembro del personal tiene una reunión de equipo o una cita personal programada para las 15:00 en un miércoles, las reservas mostrarán a ese miembro del personal como no disponible para su reserva en ese intervalo de tiempo. Ese tiempo aparecerá como ocupado o provisional en la vista de calendario de reservas, tal como se muestra en el ejemplo siguiente.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Vista de un calendario de reservas":::

> [!IMPORTANT]
> Se recomienda dejar esta configuración activada (está activada de forma predeterminada) para evitar reservas dobles y para optimizar la disponibilidad de los miembros del personal.

8. Seleccione **usar horario comercial** para establecer todas las horas bookables para que los miembros del personal solo estén dentro del horario comercial que estableció en la sección **horario comercial** de la página de información de la empresa.

    Al anular la selección de este cuadro, el personal puede recibir horas personalizadas que limitarán aún más cuando se puedan reservar. Esto es útil para los escenarios donde un miembro del personal solo puede estar en los martes y los miércoles de los sitios, o dedicar sus mañanas a un tipo de citas y a la tarde para otros tipos.
