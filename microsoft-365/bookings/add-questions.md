---
title: Agregar preguntas personalizadas y obligatorias a la página de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Si necesita hacer preguntas a los clientes cuando se concerta una cita con usted en línea, puede Agregar preguntas personalizadas y preguntas necesarias a la página de reserva.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420179"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a>Agregar preguntas personalizadas y obligatorias a la página de reserva

Las reservas le permiten crear preguntas para preguntar a los clientes cuando están reservando citas. También le permite elegir qué preguntas son necesarias.

Las preguntas se asocian con un servicio, por lo que cada servicio puede tener un conjunto diferente de preguntas. Por ejemplo, un estilo de pelo puede solicitar a los clientes que están reservando una cita para colorear el pelo si tienen alergias conocidas a blanqueamientos o matices. Esto le permite a usted y a sus clientes ahorrar tiempo cuando llegan a su cita.

Los clientes verán las preguntas personalizadas al crear su cita en la página de reserva. El personal verá las preguntas personalizadas al crear una nueva reserva desde el calendario de reservas o al ver una cita existente. Bookings guarda todas sus preguntas en una lista maestra para que no tenga que volver a crear las mismas preguntas para cada servicio. También puede elegir si las preguntas son obligatorias u opcionales.

> [!NOTE]
> Las respuestas del cliente a las preguntas se pueden ver al mirar su cita en el calendario de reserva.

Para obtener más información acerca de cómo personalizar y personalizar la página de reserva, vea [personalizar la página de reserva](customize-booking-page.md).

## <a name="add-custom-questions-to-your-services"></a>Agregar preguntas personalizadas a los servicios

1. Inicie sesión en Microsoft 365 y vaya a **reservas**.

1. Vaya a **servicios** y edite un servicio existente o **agregue un servicio**.

1. Desplácese hacia abajo hasta la sección **campos personalizados** y, a continuación, seleccione **modificar**.

   Ya hemos agregado algunas preguntas básicas sobre la información del cliente: correo electrónico del cliente, número de teléfono, dirección del cliente y notas para el cliente. La primera vez que lo haga, las preguntas de información del cliente se resaltan en gris. Esto significa que el usuario verá esta pregunta. Si selecciona la pregunta, el cuadro resaltado que hay alrededor desaparecerá y no se le preguntará al cliente.

   En este ejemplo, los números de teléfono y las notas de los clientes se han desactivado, y se han creado dos preguntas nuevas personalizadas.

   ![Imagen de la pantalla de preguntas personalizadas](../media/bookings-questions-custom-fields.png)

1. Para hacer la pregunta necesaria, active la casilla **obligatorio** . El cliente no podrá completar la reserva hasta que haya respondido a las preguntas necesarias.

1. Para crear una pregunta personalizada, seleccione **Agregar una pregunta** en la parte superior del panel. Escribe la pregunta y, a continuación, selecciona **Guardar**.

1. Haga clic en la pregunta para habilitarla. Aparece una casilla resaltada alrededor y la pregunta está habilitada.

1. Haga clic en **Aceptar** en la parte superior de la página y, a continuación, **guarde el servicio**.

Las reservas guardarán todas las preguntas personalizadas en una lista general para que pueda agregar fácilmente preguntas a cada servicio sin necesidad de escribir repetidamente las mismas preguntas. Por ejemplo, si abre un servicio diferente, la pregunta que ha creado para el primer servicio se mostrará en la sección campos personalizados, pero quedará deshabilitada. Haga clic en la pregunta para que se muestre un rectángulo resaltado y la pregunta esté habilitada.

En este ejemplo, puede ver que las preguntas que se agregaron para el primer servicio están disponibles para este servicio. Las preguntas que cree para este servicio estarán disponibles para todos los servicios.

   ![Imagen de preguntas que aparecen para varios servicios](../media/bookings-questions-services.png)

Si la página de reserva ya está publicada, no es necesario que haga nada más. Los clientes verán las preguntas la próxima vez que se pongan en el libro. Si aún no se ha publicado la página de reservas, vaya a la **Página de reserva** de Outlook en la web y, a continuación, seleccione **Guardar y publicar**.

> [!WARNING]
> También puede eliminar preguntas de la lista general. Sin embargo, si elimina una pregunta, se eliminará de todos los servicios. Le recomendamos que deshabilite la pregunta seleccionándola para asegurarse de que no afecta a ningún otro servicio. Puede ver que una pregunta está deshabilitada si no está rodeada por un rectángulo resaltado.

## <a name="customer-experience"></a>Experiencia del cliente

Cuando sus clientes le concertan una cita con usted, las preguntas básicas de información del cliente se mostrarán en la sección **Agregar sus detalles** . Las preguntas personalizadas que agregues estarán en la sección **proporcionar información adicional** .

![Imagen de lo que ven los clientes cuando las preguntas están habilitadas](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a>Experiencia del personal

Cuando sus clientes reserven una cita con usted, el personal verá las preguntas y las respuestas del cliente en el calendario de reserva. Para verlo, vaya al calendario de **reservas** \> **Calendar** y, después, abra una cita.

![Imagen de lo que el personal ve cuando las preguntas están habilitadas](../media/bookings-questions-staff.png)
