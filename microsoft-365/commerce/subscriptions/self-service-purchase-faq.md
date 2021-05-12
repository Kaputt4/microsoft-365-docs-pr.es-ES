---
title: Preguntas más frecuentes sobre la compra de autoservicio
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: Encuentre respuestas a las preguntas más frecuentes acerca de las compras de autoservicio.
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333199"
---
# <a name="self-service-purchase-faq"></a>Preguntas más frecuentes sobre la compra de autoservicio

La compra de autoservicio ofrece a los usuarios la oportunidad de probar nuevas tecnologías y desarrollar soluciones que, en última instancia, beneficien a sus organizaciones más grandes. Los equipos centrales de adquisiciones y TI tienen visibilidad para todos los usuarios que compran e implementan soluciones de compra de autoservicio a través <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">del centro Microsoft 365 administración.</a> Los administradores pueden desactivar las compras de autoservicio por producto a través de PowerShell. Para obtener más información, [vea Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

La compra de autoservicio está disponible para Power Platform (Power BI, Power Apps y Power Automate), Project y Visio.

> [!NOTE]
> La compra de autoservicio no está disponible en india ni para clientes gubernamentales o educativos. Project y Visio están disponibles para la compra de autoservicio en Brasil y la República Democrática del Congo.

## <a name="making-a-self-service-purchase"></a>Realizar una compra de autoservicio

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>¿Cómo realiza un cliente una compra de autoservicio?

Los clientes pueden realizar una compra de autoservicio en línea desde los sitios web del producto o desde mensajes de compra desde la aplicación. Primero se pide a los clientes que escriban una dirección de correo electrónico para asegurarse de que son un usuario en un inquilino Azure Active Directory (AD). A continuación, se les indica que inicien sesión con sus credenciales de Azure AD. Después de iniciar sesión, se le pide al cliente que seleccione cuántas suscripciones quiere comprar y que proporcione el pago con tarjeta de crédito. Una vez completada la compra, pueden empezar a usar su suscripción. El comprador tiene acceso a una vista limitada del centro de administración de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> donde puede asignar licencias al producto a otras personas de su organización.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>¿Cuáles son las opciones de pago para las compras de autoservicio?

Actualmente, la tarjeta de crédito es el único método de pago disponible. No se admite el pago a través de la facturación.

### <a name="who-can-buy-through-self-service-purchase"></a>Quién puede comprar a través de la compra de autoservicio?

Cualquier usuario con una cuenta de usuario no invitada en un inquilino administrado de Azure AD puede realizar una compra de autoservicio. Las compras de autoservicio no están disponibles para los inquilinos que son organizaciones gubernamentales o educativas. Si esto se aplica a su organización, no se requiere ninguna acción adicional para controlar la compra de autoservicio.

Los usuarios de organizaciones o mercados que no son aptos para la compra de autoservicio ven un mensaje pidiéndoles que se contacten con su administrador de TI.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>¿Los usuarios invitados pueden comprar a través de la compra de autoservicio?

No, los usuarios invitados no pueden completar una compra de autoservicio en un espacio empresarial en el que son invitados.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>¿Pueden los usuarios sincronizados desde una compra local de Active Directory a través de la compra de autoservicio?

Si un usuario tiene una cuenta de usuario activa en un inquilino de Azure AD elegible, puede completar una compra de autoservicio.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Quién Pueden los compradores de autoservicio asignar licencias?

Los compradores de autoservicio solo pueden asignar licencias a los usuarios del mismo inquilino de Azure AD. El comprador tiene acceso a una vista limitada del centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administración Microsoft 365</a> para asignar licencias. Los compradores pueden asignar licencias a los productos que han comprado a través de la compra de autoservicio y solo pueden asignar esas licencias a los usuarios del mismo inquilino de Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>¿Dónde ve y administra sus compras el comprador de autoservicio?

Los compradores de autoservicio pueden administrar sus compras en la vista limitada del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro Microsoft 365 administración.</a> Los compradores siempre pueden llegar  al Centro de administración desde el icono Administración del iniciador de aplicaciones integrado en todas las aplicaciones Microsoft 365 y Dynamics Online. Los compradores pueden ver las compras que han realizado, comprar suscripciones adicionales al mismo servicio y asignar licencias para esas suscripciones a otros usuarios de su organización. Además, los compradores pueden ver y pagar su factura, actualizar su método de pago y cancelar su suscripción.

## <a name="pricing"></a>Precios

### <a name="what-is-the-pricing-for-self-service-purchases"></a>¿Cuál es el precio de las compras de autoservicio?

Los precios de cada uno de los productos para la compra de autoservicio están disponibles en el sitio web de Microsoft. Los precios también se muestran como parte de la experiencia de desprotección cuando los usuarios hacen una compra de autoservicio. Estos precios pueden diferir de los precios que paga una organización al realizar compras centrales o precios ofrecidos a través de un socio.

### <a name="who-is-responsible-for-payment"></a>Quién Es responsable del pago?

La persona que compra la suscripción a través de la compra de autoservicio es la persona que se factura y quién es responsable del pago en función de los términos y precios de la compra.

## <a name="admin-capabilities"></a>Capacidades de administración

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>¿Qué capacidades tiene un administrador para las compras de autoservicio?

Los administradores pueden ver todas las compras de autoservicio realizadas en su organización en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro Microsoft 365 administración.</a> Pueden ver el producto, el nombre del comprador, las suscripciones compradas, la fecha de expiración, el historial de pedidos, el precio de compra y los usuarios asignados para cada compra de autoservicio. En el Centro de administración de Power Platform, los administradores también pueden ver la capacidad de compras de autoservicio. Si es necesario para su organización, los administradores pueden desactivar las compras de autoservicio por producto a través de PowerShell. Los administradores tienen las mismas directivas de administración de datos y acceso a los productos comprados a través de la compra de autoservicio o de forma centralizada.

Los administradores también pueden controlar si los usuarios de su organización pueden realizar compras de autoservicio. Para obtener más información, [vea Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>¿Cómo respeta Microsoft el gobierno y el cumplimiento de los datos al habilitar la compra de autoservicio?

Los administradores mantienen el control sobre qué servicios y productos están disponibles en su inquilino en función de sus requisitos de cumplimiento y gobierno de datos. Todas las directivas de acceso y administración de datos activadas por su organización se aplican a los servicios adquiridos de autoservicio disponibles.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Quién es propietario de los datos del producto creados a partir de compras sin servicio

Los datos creados a partir de productos comprados a través de la compra de autoservicio son propiedad y están controlados por la organización.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>¿Cómo centralizo las compras realizadas a través de la compra de autoservicio?

Los administradores pueden asignar licencias existentes o comprar suscripciones adicionales de productos de compra de autoservicio a través de contratos y precios existentes para los usuarios asignados a compras de autoservicio. Después de asignar estas licencias compradas de forma centralizada, los administradores pueden solicitar a los compradores que cancelen sus suscripciones existentes.

### <a name="where-does-the-admin-see-self-service-purchases"></a>¿Dónde ve el administrador las compras de autoservicio?

Los administradores globales y de facturación pueden ver las suscripciones compradas a través de la compra de autoservicio en **Facturación** Sus productos en el  >   Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administración.</a> Pueden filtrar la lista de productos para mostrar solo las suscripciones compradas a través de compras centrales o para incluir suscripciones compradas a través de la compra de autoservicio.

Los administradores pueden ver el producto, el nombre del comprador, la suscripción comprada, la fecha de expiración, el historial de pedidos, el precio de compra y los usuarios asignados.

## <a name="support-and-training"></a>Soporte técnico y formación

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>¿Se espera que los departamentos o partners de TI de los clientes admitan los productos comprados a través de la compra de autoservicio?

No se espera que los departamentos de TI y los asociados proporcionen soporte técnico para los productos comprados a través de la compra de autoservicio. Microsoft proporciona soporte estándar para los compradores de autoservicio.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Si un comprador de autoservicio llama al soporte técnico, ¿usa los incidentes de soporte premier del cliente?

Los compradores de autoservicio no usarán los incidentes de soporte premier de un cliente para recibir soporte técnico para sus compras de autoservicio.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>¿Cómo se espera que los usuarios reciban formación sobre los productos que compran a través de la compra de autoservicio?

Se proporciona una amplia formación para los usuarios en los sitios web del producto. Los productos han guiado el aprendizaje, la documentación, los ejemplos y las comunidades sólidas para obtener respuestas y sugerencias directamente de otros usuarios.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>¿Qué sucede con una compra de autoservicio si un usuario abandona la organización?

Si la persona que compró originalmente el producto de compra de autoservicio deja la organización, los usuarios válidos seguirán usando el producto al completo durante la suscripción. La suscripción permanece activa hasta que el comprador la cancela directamente o un administrador solicita la cancelación de la suscripción a través del soporte técnico del cliente. Los administradores también pueden optar por asignar una licencia comprada de forma centralizada a los usuarios de la suscripción cancelada.

## <a name="partners"></a>Asociados

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>¿Cuál es el rol de los partners de Microsoft en las compras de autoservicio?

Los partners que tienen privilegios de administración delegados pueden ver compras de autoservicio en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">el centro</a>de administración de Microsoft 365, al igual que un administrador. Los partners pueden ayudar a admitir una organización que quiere centralizar los productos comprados a través de compras de autoservicio. Además, los partners pueden ofrecer soluciones para ampliar las capacidades de una compra de autoservicio.