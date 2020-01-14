---
title: Preguntas más frecuentes sobre las compras sin asistencia
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Encuentre respuestas a las preguntas más frecuentes sobre las compras de autoservicio.
ms.custom: aka.ms/self-service-purchase-faq
ms.openlocfilehash: 8671492680eba730bf123036a4bb347d055f686d
ms.sourcegitcommit: 3c296126ba69a32af07e339f2f1eacdd8e5b878e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "41120161"
---
# <a name="self-service-purchase-faq"></a>Preguntas más frecuentes sobre las compras sin asistencia

> [!NOTE]
> La información de este artículo solo se aplica a las suscripciones de Microsoft Power Platform (Power BI, Power apps y Power Automate).

Las compras de autoservicio ahora están disponibles para Power BI en Estados Unidos.

## <a name="general"></a>General

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>¿Qué cambios presentó Microsoft en torno a las compras de autoservicio para los productos de la plataforma de energía?

El 19 de noviembre, proporcionamos a los administradores de ti una forma de desactivar la compra de autoservicio por producto a través de PowerShell. Para obtener información sobre cómo usarla, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

Para proporcionar más tiempo para prepararse para este cambio, actualizamos el lanzamiento de las funcionalidades de compra de autoservicio para que los productos de la plataforma de energía empiecen con Power BI el 14 de enero para todos los clientes de la nube comercial.  

A partir del 14 de enero de 2020, las capacidades de administración de licencias, suscripción y compra de autoservicio para los productos de la plataforma de energía (Power BI, Power apps y Power Automate) estarán disponibles para los clientes de la nube comercial en Estados Unidos. La compra de autoservicio ofrece a los usuarios una oportunidad para probar nuevas tecnologías y les permite desarrollar soluciones que beneficien a sus organizaciones más grandes. Esta capacidad no estará disponible para los inquilinos de Estados Unidos, en los que se encuentren administración pública, ONG o educación, en este momento. Las adquisiciones centrales y los equipos de ti tendrán visibilidad para todos los usuarios que compren e implementen soluciones de compra de autoservicio a través del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>y podrán desactivar la compra por parte del autoservicio por productos a través de PowerShell.

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>¿Por qué Microsoft está agregando una opción de compra de autoservicio para los productos de la plataforma de alimentación?

En el mundo actual, los usuarios finales y los departamentos están buscando cada vez más soluciones tecnológicas por su cuenta. Hemos recibido varias solicitudes de estos clientes para habilitar la compra de autoservicio de los productos de la plataforma de energía. Estamos respondiendo a la necesidad de este cliente y también equilibra las necesidades de los administradores de ti, que a menudo pierden visibilidad y control cuando los usuarios de su organización adoptan soluciones de terceros sin su conocimiento. Con la próxima funcionalidad de autoservicio para los productos de la plataforma de energía, los administradores de ti tendrán una visibilidad completa de todas las compras de autoservicio en su organización, y las directivas de gobierno de datos establecidas en el nivel de la organización se acumularán en suscripciones adquiridas a través de Self-Service. Los administradores también pueden asignar licencias existentes, o comprar suscripciones adicionales, de productos de plataforma de alimentación a través de acuerdos existentes y precios para los usuarios asignados a las compras de autoservicio. Después de asignar estas licencias adquiridas de forma centralizada, los administradores pueden solicitar que los compradores cancelen sus suscripciones existentes. Microsoft está investigando formas de simplificar y simplificar este proceso para administradores en el futuro.

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>¿Qué productos de la plataforma de energía están disponibles para la compra de servicio sin ayuda?

Microsoft ha lanzado la compra de autoservicio para Power BI para los clientes de los Estados Unidos, y los mercados adicionales están disponibles en los próximos meses. Power apps and Power Automatics se agregará a los clientes de los Estados Unidos el 28 de enero de 2020. Esta capacidad no estará disponible para los inquilinos de Estados Unidos, en los que se encuentren administración pública, ONG o educación, en este momento.

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>¿Se habilitará la compra de autoservicio para los servicios más allá de los productos de la plataforma de energía?

En este momento, solo se ofrecen los productos de la familia Power Platform a través de la compra de autoservicio.

## <a name="making-a-self-service-purchase"></a>Realizar una compra de autoservicio

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>¿Cómo realiza un cliente una compra de servicio sin ayuda?

Los clientes podrán realizar una compra de autoservicio en línea desde Microsoft Power BI, Power apps y los sitios web de Power automatizada. Se pedirá primero a los clientes que escriban una dirección de correo electrónico para asegurarse de que son usuarios de un espacio empresarial de Azure Active Directory (AD) existente. A continuación, se dirigirán para iniciar sesión con sus credenciales de Azure AD. Después de iniciar sesión, se le pedirá al cliente que seleccione el número de suscripciones que desea comprar y que proporcione pago con tarjeta de crédito. Una vez completada la compra, podrá empezar a usar su suscripción. El comprador también podrá tener acceso a una vista limitada del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a> donde puede permitir a otros usuarios de su organización usar el producto.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>¿Cuáles son las opciones de pago para las compras de servicio automático?

Actualmente, la tarjeta de crédito es el único método de pago disponible. No se admite el pago mediante facturación.

### <a name="who-can-buy-through-self-service-purchase"></a>¿Quién puede comprar a través de la compra de autoservicio?

Cualquier usuario con una cuenta de usuario no invitado en un inquilino de Azure AD administrado puede comprar. En este momento, esta capacidad no estará disponible para los inquilinos que no sean de administración pública, ONG o educación. Si esto se aplica a su organización, no es necesario realizar ninguna acción adicional para controlar la compra sin intervención del administrador en este momento.

Los usuarios de organizaciones o mercados que no son aptos para la compra de autoservicio verán un mensaje en el que se les pide que se pongan en contacto con su administrador de ti como lo hacen hoy.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>¿Pueden los invitados comprar a través de la compra de autoservicio?

No, los usuarios invitados no pueden completar una compra de autoservicio en un inquilino en el que son invitados.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>¿Pueden los usuarios sincronizarse desde un Active Directory local compre a través de una compra de autoservicio?

Si un usuario tiene una cuenta de usuario activa en un inquilino de Azure AD elegible, puede completar una compra de autoservicio.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>¿Quién puede asignar licencias a los compradores sin ayuda de autoservicio?

Los compradores de autoservicio solo podrán asignar licencias a usuarios en el mismo inquilino de Azure AD. El comprador podrá tener acceso a una vista limitada del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a> para asignar licencias. Solo tendrán visibilidad y pueden asignar licencias a los productos que hayan comprado mediante la compra de autoservicio, y solo podrán asignar esas licencias a los usuarios del mismo inquilino de Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>¿Dónde ven y administran sus compras el comprador de autoservicio?

Los compradores de autoservicio pueden administrar sus adquisiciones en la vista limitada del <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>. Los compradores siempre pueden acceder al centro de administración desde el mosaico **Administración** del iniciador de aplicaciones de Office 365 en todas las aplicaciones de Office 365 y Dynamics online. Pueden ver las compras que han realizado, comprar suscripciones adicionales al mismo servicio y asignar licencias para esas suscripciones a otros usuarios de su organización. Además, los compradores pueden ver y pagar su factura, actualizar su método de pago y cancelar su suscripción.

**Vista del centro de administración de Microsoft 365 limitado para los compradores sin servicio de asistencia:**

![Captura de pantalla del centro de administración 365 de Microsoft.](../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>Precios

### <a name="what-is-the-pricing-for-self-service-purchases"></a>¿Cuál es el precio de las compras de autoservicio?

Los precios de cada una de las plataformas de energía para las compras de autoservicio estarán disponibles en el sitio web de Microsoft y también se mostrarán como parte de la experiencia de extracción mientras se realiza una compra de autoservicio. Estos precios pueden diferir de los precios que una organización paga al realizar compras centrales o precios ofrecidos a través de un socio.

### <a name="who-is-responsible-for-payment"></a>¿Quién es el responsable del pago?

La persona que compre la suscripción a través de la compra de autoservicio se le facturará y será responsable del pago en función de las condiciones y el precio de la compra.

## <a name="admin-capabilities"></a>Capacidades de administración

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>¿Qué funcionalidades tiene un administrador para las compras de autoservicio?

Los administradores pueden ver todas las compras de autoservicio realizadas en su organización en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>. Pueden ver el producto, el nombre del comprador, las suscripciones adquiridas, la fecha de expiración, el historial de pedidos, el precio de compra y los usuarios asignados para cada una de las compras de servicios automáticos. Si es necesario para su organización, los administradores podrán desactivar las compras de autoservicio por producto a través de PowerShell. Los administradores tienen las mismas directivas de administración y acceso de datos que los productos adquiridos a través de la compra de autoservicio o de forma centralizada.

Los administradores también pueden controlar si los usuarios de su organización pueden realizar compras sin servicio de asistencia. Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>¿Cómo se respeta Microsoft el gobierno de datos y el cumplimiento mediante la habilitación de la compra de autoservicio?

Los administradores mantienen el control sobre qué servicios y productos están habilitados en su espacio empresarial en función de sus requisitos de gobierno de datos y cumplimiento normativo. Además, todas las directivas de administración de datos y de acceso, que su organización haya habilitado, se aplicarán a los servicios habilitados adquiridos de autoservicio.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>¿Quién es el propietario de los datos de producto creados a partir de las compras de autoservicio?

La organización posee y controla los datos creados a partir de productos comprados mediante la compra de autoservicio.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>¿Cómo puedo centralizar las compras hechas a través de la compra de autoservicio?

Los administradores pueden asignar licencias existentes o comprar suscripciones adicionales de productos de plataforma Power (Power BI, Power apps y Power Automate) a través de acuerdos y precios existentes para los usuarios asignados a las compras de autoservicio. Después de asignar estas licencias adquiridas de forma centralizada, los administradores pueden solicitar que los compradores cancelen sus suscripciones existentes. Microsoft está investigando formas de simplificar y simplificar este proceso para administradores en el futuro.

### <a name="where-does-the-admin-see-self-service-purchases"></a>¿Dónde ve el administrador las compras sin servicio de soporte?

Los administradores globales y de facturación pueden ver las suscripciones adquiridas a través de la compra de autoservicio en productos de **facturación** > **& Services** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a> junto con todas las demás suscripciones adquiridas a través de la adquisición central. Pueden filtrar la lista para que solo las suscripciones adquiridas a través de la adquisición central o incluir las suscripciones adquiridas a través de la compra de autoservicio.

Los administradores pueden ver el producto, el nombre del comprador, la suscripción adquirida, la fecha de expiración, el historial de la orden, el precio de compra y los usuarios asignados.

## <a name="support-and-training"></a>Soporte técnico y aprendizaje

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>¿Se espera que los socios o departamentos de TI de los clientes admitan productos adquiridos a través de la compra de autoservicio?

No se espera que los departamentos de ti y los asociados proporcionen soporte para los productos adquiridos a través de la compra de autoservicio. Microsoft proporcionará soporte técnico estándar para los compradores de autoservicio.

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>Si un comprador de autoservicio llama a soporte técnico, ¿usarán los incidentes de Soporte Premier del cliente?

Los compradores de autoservicio no podrán usar los principales incidentes de soporte técnico de los clientes para recibir soporte técnico para sus adquisiciones de autoservicio.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>¿Cómo se espera que los usuarios reciban formación en los productos que compren a través de la compra de autoservicio?

La formación exhaustiva para los usuarios se proporciona en Microsoft Power BI, Power apps y los sitios web de Power automatizada. Los productos tienen aprendizaje guiado, documentación, ejemplos y comunidades seguras para obtener respuestas y sugerencias directamente de otros usuarios.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>¿Qué pasa con una compra de autoservicio si un usuario abandona la organización?

Los usuarios válidos seguirán teniendo uso total de la compra de autoservicio mientras dure la suscripción. La suscripción permanecerá activa hasta que el comprador la cancele directamente o el administrador solicite que se cancele la suscripción a través del servicio de soporte al cliente. Los administradores también pueden elegir asignar una licencia de compra central a los usuarios de la suscripción cancelada.

## <a name="partners"></a>Asociados

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>¿Cuál es la función de los socios de Microsoft en las compras sin servicio de asistencia?

Los socios que tienen privilegios de administración delegados pueden ver las compras de autoservicio en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de Microsoft 365</a>, igual que un administrador. Los socios pueden ayudar a una organización que quiera centralizar los productos adquiridos a través de las compras de autoservicio. Además, es posible que los socios ofrezcan soluciones para ampliar las capacidades de una compra de servicio sin ayuda.