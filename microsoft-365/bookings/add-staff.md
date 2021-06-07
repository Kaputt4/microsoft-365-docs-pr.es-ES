---
title: Agregar personal a Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
description: Use esta página para crear la lista de personal y administrar los detalles de los miembros del personal, como el nombre, el número de teléfono y la dirección de correo electrónico.
ms.openlocfilehash: 23757c492986936125eff1203e6a99231164da22
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768950"
---
# <a name="add-staff-to-bookings"></a>Agregar personal a Bookings

La página Personal de Bookings es donde se crea la lista de personal y se administran los detalles de los miembros del personal, como el nombre, el número de teléfono y la dirección de correo electrónico. También puede establecer el horario laboral de cada miembro del personal desde aquí.

## <a name="before-you-begin"></a>Antes de empezar

Aunque Bookings es una característica de Microsoft 365, no todos los miembros del personal deben tener una Microsoft 365 cuenta. Todos los miembros del personal deben tener una dirección de correo electrónico válida para que puedan recibir reservas y programar cambios.

## <a name="watch-add-your-staff-to-bookings"></a>Watch: Add your staff to Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>Pasos

1. Vaya a la [página Administrar personal](https://outlook.office.com/bookings/staff) y seleccione Agregar **personal**

2. Seleccione el **botón Agregar personal.**

3. Al agregar personal desde dentro de la organización, escriba su nombre en el campo **Agregar** personas y selecciónelos cuando aparezcan en el menú desplegable. Los demás campos se rellenarán automáticamente.

    Una vez agregado un miembro del personal, puede editar el nombre que aparece en todas las comunicaciones de Bookings seleccionando la **x** junto a su nombre y editando el **campo** Agregar personas. Esto puede ser útil si desea que los miembros del personal muestren un título o un nombre específicos para los clientes, como la descripción de Adele Vance como "Dr. Vance, MD".

4. Para agregar personal de fuera de la organización, rellene manualmente su correo electrónico y otra información.

    > [!NOTE]
    > El personal de fuera de su inquilino no podrá compartir información de disponibilidad con Bookings.

5. Para cada miembro del personal, seleccione un rol: Administrador, Visor o Invitado.
    - **Los administradores** pueden editar toda la configuración, agregar y quitar personal, y crear, editar o eliminar reservas.
    - **Los visores** pueden ver todas las reservas en el calendario, pero no pueden modificarlas ni eliminarlas. Tienen acceso de solo lectura a la configuración.
    - **Los** invitados se pueden asignar a las reservas, pero no pueden abrir el buzón de reserva.

6. Seleccione **Notificar a todo el personal por correo electrónico** cuando se cree o cambie una reserva asignada para habilitar los correos electrónicos del personal. A continuación se muestra un ejemplo de correo electrónico:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Un correo electrónico de notificación de Bookings":::

7. Seleccione **Eventos en Office 365 que afecten a** la disponibilidad si desea que la información de disponibilidad de los calendarios de los miembros del personal afecte a la disponibilidad de los servicios de reservas a través de Bookings.

    Por ejemplo, si un miembro del personal tiene una reunión de equipo o una cita personal programada para las 15:00 un miércoles, Bookings mostrará a ese miembro del personal como no disponible para ser reservado en esa franja horaria. Esa hora aparecerá como ocupada o provisional en la vista de calendario Bookings, como se muestra en el ejemplo siguiente.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Vista de un calendario de Bookings":::

> [!IMPORTANT]
> Se recomienda encarecidamente dejar esta configuración activada (está activada de forma predeterminada) para evitar reservas dobles y optimizar la disponibilidad de los miembros del personal.

8. Seleccione **Usar horario comercial** para establecer todos los tiempos de reserva para que  los miembros del personal solo se ajusten al horario comercial establecido en la sección Horario comercial de la página Información empresarial.

    Al anular la selección de este cuadro, el personal puede tener horas personalizadas que limiten aún más el momento en que se pueden reservar. Esto es útil para escenarios en los que un miembro del personal solo puede estar en el sitio martes y miércoles, o dedican sus mañanas para un tipo de citas y sus tardes para otros tipos.

    > [!NOTE]
    > Solo aparecerán los primeros 31 miembros del personal que agregue a la página de personal cuando asigne miembros del personal a un servicio.

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Convertir a un usuario de Bookings en superusual sin agregarlos como personal en Bookings

Es posible que desee agregar una persona a su lista de personal en Bookings sin que esté disponible para clientes o clientes. Una vez que los conviertas en superusu usuarios, se convertirán en administradores del buzón de reserva. Ser administrador de un buzón de reserva se define como tener acceso completo y permisos de envío al buzón de reserva.

> [!NOTE]
> Estos pasos solo funcionan si el usuario que se va a agregar aún no tiene asignado un rol **de visor** en Bookings.

1. [Conectar para Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Con PowerShell, asigne acceso completo con los siguientes comandos:

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. Y, a continuación, ejecute este comando para asignar permisos de envío como.

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Este es un comando de PowerShell de ejemplo para agregar Allie Bellew al buzón de reserva de la guardería contoso.

1. Ejecute primero este comando:

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. A continuación, ejecute este comando:

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** ahora tiene acceso de administrador, pero no aparece como personal que se puede reservar en Bookings.
