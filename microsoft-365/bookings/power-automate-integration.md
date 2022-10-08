---
title: Uso de conectores de Power Automate para crear flujos de trabajo de Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.collection:
- scotvorg
description: Use los conectores de Bookings de Power Automate para crear flujos de trabajo personalizados con desencadenadores de citas.
ms.openlocfilehash: 4396b70d768e1baf104bbf22029ef739a0d71978
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68204065"
---
# <a name="use-power-automate-connectors-to-build-bookings-workflows"></a>Uso de conectores de Power Automate para crear flujos de trabajo de Bookings

Microsoft Bookings Connector está diseñado para ampliar las citas de Booking con otras funcionalidades que ofrece la plataforma eléctrica. Si alguna vez ha querido crear flujos de trabajo personalizados para las citas de clientes empresariales, por ejemplo, permitir a los clientes reservar una reunión de Zoom junto con una cita, integrar un método de pago mediante Stripe, cargar datos de clientes en un sistema CRM o enviar correos electrónicos de bienvenida, Bookings Connector es su solución de Bookings.

## <a name="before-you-begin"></a>Antes de empezar

Los clientes que quieran usar Bookings Connector deben tener una licencia de Bookings. Para obtener más información sobre las licencias y suscripciones de Microsoft Bookings, consulte [Microsoft Bookings preguntas más frecuentes](bookings-faq.yml#is-bookings-available-for-my-subscription-).

Microsoft Bookings usa la autenticación de Azure Active Directory (AAD). Una cuenta válida de Microsoft 365 garantiza que está autenticado para usar Bookings Connector. Debe iniciar sesión para crear flujos basados en citas.

Para crear un flujo personalizado que use citas de Bookings como desencadenadores, debe proporcionar la dirección SMTP empresarial de Bookings.

![Imagen de una dirección SMTP.](media/bookings-teams-smtp.png)

## <a name="get-started-with-connectors"></a>Introducción a los conectores

Estos son algunos de los flujos comunes que puede compilar con conectores de Microsoft Bookings:

### <a name="integration-with-stripe"></a>Integración con Stripe

Stripe permite a particulares y empresas aceptar pagos a través de Internet. Puede realizar un seguimiento de clientes, pedidos, facturas y mucho más. Para obtener más información, vea [Stripe | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_stripe/stripe/).

### <a name="integration-with-zoom"></a>Integración con Zoom

El conector zoom meetings ayuda a automatizar las operaciones de reunión de Zoom. Para obtener más información, consulte [Zoom Meetings (Independent Publisher) | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_zoommeetingsip/zoom-meetings-independent-publisher/).

### <a name="integration-with-dynamic-365"></a>Integración con Dynamic 365

Dynamics 365 Sales Insights ayuda a aumentar las ventas con la ayuda de información basada en inteligencia artificial (IA) que promueve la participación personalizada y la toma de decisiones proactivas para ayudar a crear relaciones. Para obtener más información, consulte [Dynamics 365 Sales Insights | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_assistantstudio/dynamics-365-sales-insights/).

Para ver todos los conectores de Bookings disponibles, consulte [Conectores admitidos | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/).

## <a name="known-issues-and-limitations"></a>Problemas y limitaciones conocidos

- **Solo los administradores pueden crear flujos mediante desencadenadores de cita.** Solo los administradores de Bookings pueden crear desencadenadores de citas. Si es un usuario y no un administrador (miembro del equipo, programador, visor, invitado), debe pedir al administrador que cree un flujo. Como alternativa, también puede solicitar acceso de administrador.

- **Solo se pueden crear cinco flujos por buzón de Bookings.** Este es un límite de nivel de buzón de Bookings y no un límite por administrador. Si desea más de una acción para un desencadenador de cita, puede agregar la acción a uno de los flujos existentes con el botón **Agregar acción** . Para obtener soporte técnico, póngase en contacto con otros administradores de Booking.

- **Algunos parámetros de Bookings no se rellenan.** Cancelar motivo y Notas personalizadas para reservas 1:1 no se rellenan. La corrección para esto se implantará pronto.

- **Los códigos de error durante la creación del flujo no son totalmente visibles.** Los errores que pueden producirse durante la creación de un flujo no aparecen en el portal de flujo. La corrección para esto está en curso y estará disponible en la próxima versión.

## <a name="common-errors-and-remedies"></a>Errores y soluciones comunes

Códigos de error HTTP al crear flujos:

- '401': compruebe si hay problemas relacionados con la autenticación en la conexión.
- '403': solo los administradores de Bookings pueden crear flujos de citas. Consulte el primer problema en "Problemas y limitaciones conocidos" anteriormente.
- '403': El dominio de dirección URL de notificación no forma parte de la lista permitida.
- '429': se ha creado más del número esperado de flujos de citas para una empresa. Consulte el límite de cinco flujos por buzón de Bookings en "Problemas conocidos y limitaciones" anteriormente.
- '500': se trata de un error interno del servidor. Informe de este error al ingeniero de soporte técnico e incluya los detalles del error en la respuesta de creación del flujo.

## <a name="frequently-asked-questions"></a>preguntas más frecuentes

**Cómo obtener la dirección SMTP para crear un flujo basado en desencadenador de cita?**

Para crear flujos basados en desencadenadores de citas, el creador debe obtener la dirección SMTP de la empresa bookings. Esta es la misma dirección SMTP que se usa para realizar llamadas de grafos. También forma parte de la dirección URL de la página Bookings.

**¿Cómo puedo obtener datos de clientes de las respuestas del desencadenador de citas?**

Para una reserva 1:1, están disponibles campos de nivel superior como CustomerName, CustomerEmail, etc. Para una reserva de grupo, la matriz de clientes puede usar campos como displayName, correo electrónico de los clientes, nombreDeEquipo de los clientes, etc. con un componente de bucle de Power Automate.

**¿Por qué StaffMembers es una matriz?**

Puede asignar más de un miembro del personal como host. Si el servicio solo tiene un miembro del personal asignado como anfitrión, los detalles del personal se ven en la matriz de miembros del personal.

## <a name="related-content"></a>Contenido relacionado

[Conectores de Microsoft Power Automate](https://make.preview.powerautomate.com/connectors/shared_microsoftbookings/microsoft-bookings/)\
[Referencia de Microsoft Bookings (versión preliminar)](/connectors/microsoftbookings/) (artículo)