---
title: Agregar preguntas personalizadas y requeridas a la página de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Si necesita hacer preguntas a los clientes cuando reserven una cita con usted en línea, puede agregar preguntas personalizadas y preguntas necesarias a la página de reserva.
ms.openlocfilehash: 9830dfaa9ac1964e74eb16321d061e096aad1bab
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714623"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a>Agregar preguntas personalizadas y requeridas a la página de reserva

> [!NOTE]
> Este artículo le ayuda a interactuar con la versión más reciente de Microsoft Bookings. Las versiones anteriores se retirarán en los próximos meses.

Bookings le permite crear preguntas para hacerles a sus clientes cuando están reservando citas. También le permite elegir qué preguntas son necesarias.

Las preguntas se asocian a un servicio, por lo que cada servicio puede tener un conjunto diferente de preguntas. Por ejemplo, un estilista de pelo puede preguntar a los clientes que están reservando una cita para colorear el cabello si tienen alergias conocidas a lejías o tintes. Esto le permite a usted y a sus clientes ahorrar tiempo cuando llegan a su cita.

Los clientes verán las preguntas personalizadas al crear su cita en la página de reserva. El personal verá las preguntas personalizadas cuando cree una nueva reserva desde el calendario de Bookings o cuando vea una cita existente. Bookings guarda todas las preguntas en una lista maestra para que no tenga que volver a crear las mismas preguntas para cada servicio. También puede elegir si las preguntas son necesarias u opcionales.

> [!NOTE]
> Las respuestas del cliente a las preguntas se pueden ver al consultar su cita en el calendario de reserva.

Para obtener más información sobre cómo personalizar y personalizar la página de reserva, consulte [Personalización de la página de reserva](customize-booking-page.md).

## <a name="add-custom-questions-to-your-services"></a>Adición de preguntas personalizadas a los servicios

1. Inicie sesión en Microsoft 365 y vaya a **Bookings**.

1. Elija el calendario.

1. Vaya a **Servicios** y edite un servicio existente o **Agregar un servicio**.

1. Elija la sección **Campos personalizados** .

   Ya hemos agregado algunas preguntas básicas sobre la información del cliente: correo electrónico del cliente, número de teléfono, dirección de cliente y notas del cliente. La primera vez que lo hace, las preguntas de información del cliente se resaltan en gris. Esto significa que el usuario verá esta pregunta. Si selecciona la pregunta, el cuadro de resaltado alrededor de ella desaparecerá y no se le hará esa pregunta al cliente.

   En este ejemplo, el número de teléfono y las notas del cliente se han desactivado y hemos creado dos nuevas preguntas personalizadas que se deben formular.

   ![Imagen de la pantalla de preguntas personalizadas.](../media/bookings-questions-custom-fields.png)

1. Para hacer que la pregunta sea necesaria, active la casilla **Requerido** . El cliente no podrá completar la reserva hasta que haya respondido a las preguntas necesarias.

1. Para crear una pregunta personalizada, seleccione **Agregar una pregunta** en la parte superior del panel. Escriba la pregunta y, a continuación, seleccione **Guardar**.

1. Haga clic en la pregunta para habilitarla. Aparece un cuadro resaltado alrededor de él y la pregunta está habilitada.

1. Haga clic en **Aceptar** en la parte superior de la página y, a continuación, **guarde el servicio**.

Bookings guardará todas las preguntas personalizadas en una lista maestra para que pueda agregar fácilmente preguntas a cada servicio sin necesidad de escribir repetidamente las mismas preguntas. Por ejemplo, si abre un servicio diferente, la pregunta que creó para el primer servicio se mostrará en la sección Campos personalizados, pero se deshabilitará. Haga clic en la pregunta para que se muestre un rectángulo resaltado y la pregunta esté habilitada.

En este ejemplo, puede ver que las preguntas que se agregaron para el primer servicio están disponibles para este servicio. Las preguntas que cree para este servicio estarán disponibles para todos los servicios.

   ![Imagen de las preguntas que aparecen para varios servicios.](../media/bookings-questions-services.png)

Si la página de reserva ya está publicada, no es necesario hacer nada más. Los clientes verán las preguntas la próxima vez que reserven con usted. Si la página de reserva aún no está publicada, vaya a la **página de reserva** desde Outlook en la Web y, a continuación, seleccione **Guardar y publicar**.

> [!WARNING]
> También puede eliminar preguntas de la lista maestra. Sin embargo, si elimina una pregunta, se eliminará de todos los servicios. Se recomienda deshabilitar la pregunta seleccionándola para asegurarse de que no afecta a ningún otro servicio. Puede ver que una pregunta está deshabilitada si no está rodeada por un rectángulo resaltado.

## <a name="customer-experience"></a>Experiencia del cliente

Cuando los clientes reserven una cita con usted, las preguntas de información básica del cliente se mostrarán en la sección **Agregar sus detalles** . Las preguntas personalizadas que agregue estarán en la sección **Proporcionar información adicional** .

![Imagen de lo que ven los clientes cuando se habilitan las preguntas.](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a>Experiencia del personal

Cuando los clientes reserven una cita con usted, su personal verá las preguntas y las respuestas del cliente en el calendario de reserva. Para verlo, vaya a **Bookings** \> **Calendario** y abra una cita.

![Imagen de lo que el personal ve cuando se habilitan las preguntas.](../media/bookings-questions-staff.png)
