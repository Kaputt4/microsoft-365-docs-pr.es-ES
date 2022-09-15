---
title: Entender los perfiles de facturación
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: amberb, vikdesai
audience: Admin
ms.topic: article
f1.keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: Obtenga información sobre cómo los perfiles de facturación admiten facturas.
ms.date: 04/02/2021
ms.openlocfilehash: 34e56474106974e543640eb25b2cea4db0a2efc8
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67711398"
---
# <a name="understand-billing-profiles"></a>Entender los perfiles de facturación

Un perfil de facturación contiene un método de pago, información de facturación y otras configuraciones de factura, como el número de pedido de compra y las preferencias de factura por correo electrónico. Usa un perfil de facturación para pagar los productos que compra a Microsoft. Los perfiles de facturación se crean automáticamente y cada uno se factura por separado. 

> [!NOTE]
>
> No todas las cuentas tienen un perfil de facturación. Si no está seguro de si tiene uno, puede [ver una lista de los perfiles de facturación](manage-billing-profiles.md#view-my-billing-profiles).

## <a name="what-are-billing-profile-roles"></a>¿Qué son los roles de perfil de facturación?

Los roles de los perfiles de facturación tienen permisos para controlar las compras y ver y administrar facturas. Asigne estos roles a los usuarios que realicen un seguimiento, organicen y paguen facturas. Por ejemplo, los miembros del equipo de adquisiciones de su organización.

| Role                         | Descripción                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Propietario del perfil de facturación        | Administrar todo para un perfil de facturación                                          |
| Colaborador del perfil de facturación  | Administrar todo excepto los permisos de un perfil de facturación                        |
| Lector de perfil de facturación       | Vista de solo lectura de todo en un perfil de facturación                                |
| Administrador de facturas              | Ver y pagar facturas, y tiene una vista de solo lectura de todo en un perfil de facturación  |

## <a name="view-my-billing-profiles"></a>Visualización de mis perfiles de facturación

> [!NOTE]
>
> Si sigue estos pasos y la lista de perfiles de facturación está vacía, significa que no tiene un perfil de facturación y no puede usar esta característica.

1. En el Centro de administración, vaya a la página **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.
2. Seleccione la pestaña **Perfil de facturación** y, a continuación, seleccione un perfil de facturación en la lista.

Cada perfil de facturación incluye la siguiente información:

- Nombre y estado &ndash; **del perfil de facturación** Nombre único del perfil de facturación y si el perfil de facturación está activo o deshabilitado para la compra.
- **Configuración de factura** &ndash; Moneda basada en el país de la cuenta de facturación, información sobre la frecuencia y la fecha de la factura, la opción de recibir facturas como datos adjuntos de correo electrónico y un campo de número de pedido de compra opcional
- **Métodos** &ndash; de pago Muestra el método de pago principal y de copia de seguridad, si existe, para el perfil.
- &ndash; **Cuenta de facturación** Nombre de la cuenta de facturación con la que está relacionado el perfil. Para obtener más información sobre las cuentas de facturación, consulte [Descripción de las cuentas de facturación](../manage-billing-accounts.md).
- &ndash; **Información de contacto** Dirección de facturación, nombre de contacto y dirección de correo electrónico
- Roles &ndash; **de perfil de facturación** Una lista de personas a las que se asigna uno de los roles de perfil de facturación para hacer cosas para ese perfil. Por ejemplo, pagar facturas, agregar un número de pedido de compra o reemplazar el método de pago que se usa para realizar compras.

> [!NOTE]
>
> Solo puede asignar roles de perfil de facturación a los usuarios de su organización.

## <a name="need-help-contact-support"></a>¿Necesita ayuda? Ponerse en contacto con soporte técnico

Si tiene preguntas o necesita ayuda con los cargos de Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">cree una solicitud de soporte técnico con Soporte técnico de Azure</a>.

Si tiene preguntas o necesita ayuda con su perfil de facturación en Centro de administración de Microsoft 365, [póngase en contacto con el soporte técnico](../../admin/get-help-support.md).

## <a name="related-content"></a>Contenido relacionado

[Cómo pagar la suscripción con un perfil de facturación](pay-for-subscription-billing-profile.md) (artículo)\
[Descripción de las cuentas de facturación](../manage-billing-accounts.md) (artículo)\
[Administración de métodos de pago](manage-payment-methods.md) (artículo)
