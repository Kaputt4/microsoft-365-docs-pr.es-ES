---
title: Entender los perfiles de facturación
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Obtenga información sobre cómo los perfiles de facturación admiten facturas.
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537336"
---
# <a name="understand-billing-profiles"></a>Entender los perfiles de facturación

Un perfil de facturación contiene un método de pago, información de facturación y otras opciones de facturación, como el número de pedido de compra y la preferencia de factura de correo electrónico. Usas un perfil de facturación para pagar los productos que compras a Microsoft. Un perfil de facturación se crea automáticamente cuando un usuario realiza una compra de autoservicio. Cada perfil de facturación se factura por separado.

> [!NOTE]
>
> Los perfiles de facturación no están disponibles para los clientes  que compren productos y servicios de Microsoft.com o en la página Servicios de compra del centro de administración Microsoft 365 administración.

## <a name="what-are-billing-profile-roles"></a>¿Qué son los roles de perfil de facturación?

Los roles de los perfiles de facturación tienen permisos para controlar las compras y ver y administrar facturas. Asigne estos roles a los usuarios que realicen un seguimiento, organicen y paguen facturas. Por ejemplo, los miembros del equipo de compras de la organización.

| Función                         | Descripción                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Propietario del perfil de facturación        | Administrar todo para un perfil de facturación                                          |
| Colaborador de perfiles de facturación  | Administrar todo excepto los permisos en un perfil de facturación                        |
| Lector de perfiles de facturación       | Vista de solo lectura de todo en un perfil de facturación                                |
| Administrador de facturas              | Ver y pagar facturas y tiene una vista de solo lectura de todo en un perfil de facturación  |

## <a name="view-my-billing-profiles"></a>Ver mis perfiles de facturación

> [!NOTE]
>
> Si sigues estos pasos y la lista de perfiles de facturación está vacía, significa que no tienes un perfil de facturación y no puedes usar esta característica.

1. En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.
2. Seleccione la **pestaña Perfil de facturación** y, a continuación, seleccione un perfil de facturación de la lista.

Cada perfil de facturación incluye la siguiente información:

- **Nombre y estado del perfil de facturación** &ndash; Nombre único del perfil de facturación y si el perfil de facturación está activo o deshabilitado para la compra.
- **Configuración de factura** &ndash; Moneda basada en el país de la cuenta de facturación, información sobre la frecuencia y la fecha de facturación, la opción de recibir facturas como datos adjuntos de correo electrónico y un campo de número de pedido opcional
- **Métodos de pago** &ndash; Muestra el método de pago principal y de copia de seguridad, si lo hay, para el perfil
- **Cuenta de facturación** &ndash; Nombre de la cuenta de facturación a la que está relacionado el perfil. Para obtener más información acerca de las cuentas de facturación, vea [Comprender cuentas de facturación.](../manage-billing-accounts.md)
- **Información de contacto** &ndash; Dirección de facturación y nombre de contacto y dirección de correo electrónico
- **Roles de perfil de facturación** &ndash; Una lista de personas a las que se asigna uno de los roles de perfil de facturación para hacer cosas para ese perfil. Por ejemplo, pagar facturas, agregar un número de PEDIDO o reemplazar el método de pago que se usa para realizar compras.

> [!NOTE]
>
> Solo puede asignar roles de perfil de facturación a los usuarios de su organización.

## <a name="need-help-contact-support"></a>¿Necesita ayuda? Ponerse en contacto con soporte técnico

Si tiene preguntas o necesita ayuda con los cargos de Azure, cree una solicitud de soporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">técnico con soporte técnico de Azure</a>.

Si tiene preguntas o necesita ayuda con su perfil de facturación en Microsoft 365 centro de administración, póngase [en contacto con el soporte técnico](../../business-video/get-help-support.md).

## <a name="related-content"></a>Contenido relacionado

[Cómo pagar la suscripción con un perfil de facturación](pay-for-subscription-billing-profile.md) (artículo)\
[Comprender cuentas de facturación](../manage-billing-accounts.md) (artículo)\
[Administrar métodos de pago](manage-payment-methods.md) (artículo)
