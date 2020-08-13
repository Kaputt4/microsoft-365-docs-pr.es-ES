---
title: Preguntas más frecuentes sobre las compras sin asistencia
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: Encuentre respuestas a las preguntas más frecuentes sobre las compras de autoservicio.
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653706"
---
# <a name="self-service-purchase-faq"></a>Preguntas más frecuentes sobre las compras sin asistencia

La compra de autoservicio ofrece a los usuarios una oportunidad para probar nuevas tecnologías y desarrollar soluciones que beneficien en última instancia a sus organizaciones más grandes. Las adquisiciones centrales y los equipos de TI tienen visibilidad para todos los usuarios que compren e implementen soluciones de compra de autoservicio a través del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>. Los administradores pueden desactivar la opción de compra por parte del servicio por cada producto a través de PowerShell. Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

La compra de autoservicio está disponible para la plataforma de alimentación (Power BI, Power apps y Power Automate), Project y Visio.

> [!NOTE]
> La compra de autoservicio no está disponible en India, y no está disponible para los clientes de la administración pública o educativa.

## <a name="making-a-self-service-purchase"></a>Realizar una compra de autoservicio

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>¿Cómo realiza un cliente una compra de servicio sin ayuda?

Los clientes pueden realizar una compra de autoservicio en línea desde los sitios web del producto o desde los mensajes de compra desde la aplicación. Primero se solicita a los clientes que escriban una dirección de correo electrónico para asegurarse de que son usuarios de un espacio empresarial de Azure Active Directory (AD) existente. A continuación, se les dirige a iniciar sesión con sus credenciales de Azure AD. Después de iniciar sesión, se le pedirá al cliente que seleccione el número de suscripciones que desea comprar y que proporcione un pago con tarjeta de crédito. Una vez completada la compra, puede empezar a usar su suscripción. El comprador tiene acceso a una vista limitada del centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administración de Microsoft 365</a> donde puede asignar licencias al producto a otros usuarios de la organización.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>¿Cuáles son las opciones de pago para las compras de servicio automático?

Actualmente, la tarjeta de crédito es el único método de pago disponible. No se admite el pago a través de facturación.

### <a name="who-can-buy-through-self-service-purchase"></a>¿Quién puede comprar a través de la compra de autoservicio?

Cualquier usuario con una cuenta de usuario no invitado en un inquilino de Azure AD administrado puede realizar una compra de autoservicio. La compra de autoservicio no está disponible para los inquilinos que son organizaciones gubernamentales o educativas. Si esto se aplica a su organización, no es necesario realizar ninguna acción adicional para controlar la compra de servicios sin intervención del administrador.

Los usuarios de organizaciones o mercados que no son aptos para la compra de autoservicio ven un mensaje que les pide que se pongan en contacto con su administrador de ti.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>¿Pueden los invitados comprar a través de la compra de autoservicio?

No, los usuarios invitados no pueden completar una compra de autoservicio en un inquilino en el que son invitados.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>¿Pueden los usuarios sincronizarse desde un Active Directory local compre a través de una compra de autoservicio?

Si un usuario tiene una cuenta de usuario activa en un inquilino de Azure AD elegible, puede completar una compra de autoservicio.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>¿Quién puede asignar licencias a los compradores sin ayuda de autoservicio?

Los compradores de autoservicio solo pueden asignar licencias a usuarios en el mismo inquilino de Azure AD. El comprador tiene acceso a una vista limitada del centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administración de Microsoft 365</a> para asignar licencias. Los compradores pueden asignar licencias a esos productos que han comprado mediante la compra de autoservicio y solo pueden asignar esas licencias a los usuarios en el mismo inquilino de Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>¿Dónde ven y administran sus compras el comprador de autoservicio?

Los compradores de autoservicio pueden administrar sus adquisiciones en la vista limitada del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>. Los compradores siempre pueden acceder al centro de administración desde el icono de **Administración** en el iniciador de aplicaciones integrado en todas las aplicaciones de Microsoft 365 y Dynamics online. Los compradores pueden ver las compras que han realizado, comprar suscripciones adicionales al mismo servicio y asignar licencias para esas suscripciones a otros usuarios de su organización. Además, los compradores pueden ver y pagar su factura, actualizar su método de pago y cancelar su suscripción.

## <a name="pricing"></a>Precios

### <a name="what-is-the-pricing-for-self-service-purchases"></a>¿Cuál es el precio de las compras de autoservicio?

El precio de cada uno de los productos para la compra de servicios automáticos está disponible en el sitio web de Microsoft. Los precios también se muestran como parte de la experiencia de desprotección cuando los usuarios realizan una compra de autoservicio. Estos precios pueden diferir de los precios que una organización paga al realizar compras centrales o precios ofrecidos a través de un socio.

### <a name="who-is-responsible-for-payment"></a>¿Quién es el responsable del pago?

La persona que adquiere la suscripción mediante la compra de autoservicio es la persona que se factura y quién es responsable del pago en función de los términos y el precio de la compra.

## <a name="admin-capabilities"></a>Capacidades de administración

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>¿Qué funcionalidades tiene un administrador para las compras de autoservicio?

Los administradores pueden ver todas las compras de autoservicio realizadas en su organización en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>. Pueden ver el producto, el nombre del comprador, las suscripciones adquiridas, la fecha de expiración, el historial de pedidos, el precio de compra y los usuarios asignados para cada una de las compras de servicios automáticos. En el centro de administración de la plataforma de energía, los administradores también pueden ver la capacidad de las compras sin ayuda del servicio. Si es necesario para su organización, los administradores pueden desactivar las compras de autoservicio por producto a través de PowerShell. Los administradores tienen las mismas directivas de administración y acceso de datos que los productos adquiridos a través de la compra de autoservicio o de forma centralizada.

Los administradores también pueden controlar si los usuarios de su organización pueden realizar compras sin servicio de asistencia. Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>¿Cómo se respeta Microsoft el gobierno de datos y el cumplimiento mediante la habilitación de la compra de autoservicio?

Los administradores mantienen el control sobre los servicios y productos disponibles dentro de su espacio empresarial en función de sus requisitos de gobierno de datos y cumplimiento normativo. Se aplican todas las directivas de administración de datos y acceso que su organización activó a los servicios adquiridos de autoservicio disponibles.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>¿Quién es el propietario de los datos de producto creados a partir de las compras de autoservicio?

La organización posee y controla los datos creados a partir de productos comprados mediante la compra de autoservicio.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>¿Cómo puedo centralizar las compras hechas a través de la compra de autoservicio?

Los administradores pueden asignar licencias existentes o comprar suscripciones adicionales de productos de compra de autoservicio a través de contratos y precios existentes para usuarios asignados a las compras de autoservicio. Después de asignar estas licencias adquiridas de forma centralizada, los administradores pueden solicitar que los compradores cancelen sus suscripciones existentes.

### <a name="where-does-the-admin-see-self-service-purchases"></a>¿Dónde ve el administrador las compras sin servicio de soporte?

Los administradores globales y de facturación pueden ver las suscripciones adquiridas a través de la compra de autoservicio en la **facturación**de los  >  **productos** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de 365 de Microsoft</a>. Pueden filtrar la lista productos para que solo se muestren las suscripciones adquiridas a través de la adquisición central o para incluir las suscripciones que se hayan comprado a través de la compra de autoservicio.

Los administradores pueden ver el producto, el nombre del comprador, la suscripción adquirida, la fecha de expiración, el historial de la orden, el precio de compra y los usuarios asignados.

## <a name="support-and-training"></a>Soporte técnico y aprendizaje

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>¿Se espera que los socios o departamentos de TI de los clientes admitan productos adquiridos a través de la compra de autoservicio?

No se espera que los departamentos de ti y los asociados proporcionen soporte para los productos adquiridos a través de la compra de autoservicio. Microsoft proporciona soporte técnico estándar para los compradores de autoservicio.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Si un comprador de autoservicio llama a soporte técnico, ¿se usan los incidentes de Soporte Premier del cliente?

Los compradores de autoservicio no podrán usar los principales incidentes de soporte técnico de los clientes para recibir soporte técnico para sus adquisiciones de autoservicio.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>¿Cómo se espera que los usuarios reciban formación en los productos que compren a través de la compra de autoservicio?

En los sitios web del producto se proporciona una amplia capacitación para los usuarios. Los productos tienen aprendizaje guiado, documentación, ejemplos y comunidades seguras para obtener respuestas y sugerencias directamente de otros usuarios.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>¿Qué pasa con una compra de autoservicio si un usuario abandona la organización?

Si la persona que compró originalmente el producto de compra sin servicio sale de la organización, los usuarios válidos seguirán teniendo uso completo del producto durante el período de suscripción. La suscripción permanece activa hasta que el comprador la cancela directamente o un administrador solicita la cancelación de la suscripción a través del soporte técnico al cliente. Los administradores también pueden elegir asignar una licencia de compra central a los usuarios de la suscripción cancelada.

## <a name="partners"></a>Asociados

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>¿Cuál es la función de los socios de Microsoft en las compras sin servicio de asistencia?

Los socios que tienen privilegios de administración delegados pueden ver las compras de autoservicio en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>, igual que un administrador. Los socios pueden ayudar a una organización que quiera centralizar los productos adquiridos a través de las compras de autoservicio. Además, es posible que los socios ofrezcan soluciones para ampliar las capacidades de una compra de servicio sin ayuda.