---
title: Agregar personal a Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
description: Use esta página para crear la lista de personal y administrar los detalles de los miembros del personal, como el nombre, el número de teléfono y la dirección de correo electrónico.
ms.openlocfilehash: dbdf0be6c08c0ed0bf0ef7ce22a415d7728cd93d
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730455"
---
# <a name="add-staff-to-bookings"></a>Agregar personal a Bookings

En la página Personal de Bookings se crea la lista de personal y se administran los detalles de los miembros del personal, como el nombre, el número de teléfono y la dirección de correo electrónico. También puede establecer horas de trabajo para cada miembro del personal desde aquí.

## <a name="before-you-begin"></a>Antes de empezar

Aunque Bookings es una característica de Microsoft 365, no todos los miembros del personal deben tener una cuenta de Microsoft 365. Todos los miembros del personal deben tener una dirección de correo electrónico válida para que puedan recibir reservas y cambios en la programación.

## <a name="watch-add-your-staff-to-bookings"></a>Ver: Incorporación de su personal a Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>Pasos

1. Elija su calendario en la página principal.

2. Vaya a la opción personal en el panel izquierdo y seleccione **Agregar nuevo personal**.

3. Al agregar personal desde dentro de la organización, escriba su nombre en el campo **Agregar personas** y selecciónelos cuando aparezcan en el menú desplegable. Los demás campos se rellenarán automáticamente.

    Una vez que se agrega un miembro del personal, puede editar el nombre que aparece en todas las comunicaciones de Bookings seleccionando la **x** junto a su nombre y editando el campo **Agregar personas** . Esto puede ser útil si desea que los miembros del personal muestren un título o nombre específico para los clientes, como la descripción de Adele Vance como "Dr. Vance, MD".

4. Para agregar personal de fuera de la organización, rellene manualmente su correo electrónico y otra información.

    > [!NOTE]
    > El personal de fuera de su inquilino no podrá compartir información de disponibilidad con Bookings.

5. Para cada miembro del personal, seleccione un rol: Miembro del equipo, Programador, Visor o Invitado.
    - **Los miembros del equipo** pueden administrar las reservas en su propio calendario y su disponibilidad en el buzón de reserva. Al agregar o editar una reserva en su calendario, se les asignará como personal.
    - **Scheduler** puede administrar las reservas en el calendario y los detalles del cliente. Tienen acceso de solo lectura a la configuración, al personal y a los servicios.
    - **El visor** puede ver todas las reservas en el calendario, pero no pueden modificarlas ni eliminarlas. Tienen acceso de solo lectura a la configuración.
    - **Los huéspedes** pueden ser asignados a las reservas, pero no pueden abrir el buzón de reserva.

6. Seleccione **Notificar a todo el personal por correo electrónico cuando se cree o cambie una reserva asignada a ellos** para habilitar los correos electrónicos del personal. A continuación se muestra un correo electrónico de ejemplo:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Un correo electrónico de notificación de Bookings.":::

7. Seleccione **Eventos en Office 365 calendario afectará a la disponibilidad** si desea que la información de disponibilidad de los calendarios de los miembros del personal afecte a la disponibilidad de los servicios de reservas a través de Bookings.

    Por ejemplo, si un miembro del personal tiene una reunión de equipo o una cita personal programada para las 3 p. m. de un miércoles, Bookings mostrará que el miembro del personal no está disponible para reservarse en esa franja horaria. Ese tiempo aparecerá como ocupado o provisional en la vista de calendario de Bookings, como se muestra en el ejemplo siguiente.

    :::image type="content" source="media/bookings-busy-tentative-view-2.png" alt-text="Vista de un calendario de Bookings.":::

> [!IMPORTANT]
> Se recomienda encarecidamente dejar esta opción activada (está activada de forma predeterminada) para evitar las reservas dobles y optimizar la disponibilidad de los miembros del personal.

8. Seleccione **Usar horas laborables** para establecer todos los tiempos que se pueden reservar para que los miembros del personal solo estén dentro del horario comercial que establezca en la sección **Horario comercial** de la página Información empresarial.

    Al anular la selección de este cuadro, el personal puede recibir horas personalizadas que limiten aún más cuando se puedan reservar. Esto es útil para escenarios en los que un miembro del personal solo puede estar en el sitio los martes y miércoles, o dedica sus mañanas para un tipo de citas, y sus tardes para otros tipos.

    > [!NOTE]
    > Bookings admite hasta 100 miembros del personal en un calendario de reservas.

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Convertir a un usuario de Bookings en superusuario sin agregarlo como personal en Bookings

Es posible que quiera agregar una persona a su lista de personal en Bookings sin ponerla a disposición de clientes o clientes. Una vez que los convierta en superusuario, se convertirán en administrador del buzón de reserva. Ser administrador de un buzón de reserva se define como tener permisos de acceso completo y envío como al buzón de reserva.

> [!NOTE]
> Estos pasos solo funcionan si el usuario que se va a agregar aún no tiene asignado un rol de **visor** en Bookings.

1. [Conéctese a Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Con PowerShell, asigne acceso completo con los siguientes comandos:

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. A continuación, ejecute este comando para asignar permisos de envío como.

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Este es un comando de PowerShell de ejemplo para agregar Allie Bellew al buzón de reserva de guardería de Contoso.

1. Ejecute primero este comando:

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. A continuación, ejecute este comando:

    ```powershell
    Add-RecipientPermission -Identity "daycare@contoso.com" -Trustee "Allie Bellew" -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** ahora tiene acceso de administrador, pero no aparece como personal reservable en Bookings.
