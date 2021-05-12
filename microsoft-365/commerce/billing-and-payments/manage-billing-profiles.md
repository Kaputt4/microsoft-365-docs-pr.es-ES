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
ms.openlocfilehash: 36d762e50627763b7856ed1fe6c109e8da2b4789
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332035"
---
# <a name="understand-billing-profiles"></a>Entender los perfiles de facturación

Para los clientes comerciales que compran productos y servicios de Microsoft, los perfiles de facturación te permiten personalizar qué elementos se incluyen en la factura y cómo pagas tus facturas.

Los perfiles de facturación incluyen la siguiente información:

- **Cuenta de facturación** &ndash; Nombre de la cuenta de facturación con la que está relacionado el perfil
- **Métodos de pago** &ndash; Tarjetas de crédito o débito, cuentas bancarias, cheque o transferencia bancaria
- **Información de contacto** &ndash; Dirección de facturación y un nombre de contacto
- **Configuración de factura** &ndash; Moneda basada en el país de la cuenta de facturación, un número de PEDIDO opcional y la opción de recibir facturas como datos adjuntos de correo electrónico
- **Permisos** &ndash; Permisos que le permiten cambiar el perfil de facturación, pagar facturas o usar el método de pago en el perfil de facturación para realizar compras

Usa perfiles de facturación para controlar tus compras y personalizar la factura. Se genera una factura mensual para los productos comprados con el perfil de facturación. Puede personalizar la factura, como actualizar el número de pedido de compra y la preferencia de factura de correo electrónico.

Se crea automáticamente un perfil de facturación para tu cuenta de facturación durante la primera compra. Puede crear perfiles de facturación en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfiles de facturación</a> para configurar más facturas. Por ejemplo, puede usar diferentes perfiles de facturación al realizar compras para cada departamento de su organización. En la próxima fecha de facturación, recibirás una factura para cada perfil de facturación.

## <a name="billing-profile-roles"></a>Roles de perfil de facturación

Los roles de los perfiles de facturación tienen permisos para controlar las compras y ver y administrar facturas. Asigne estos roles a los usuarios que realicen un seguimiento, organicen y paguen facturas, como los miembros del equipo de compras de la organización.

| Role                         | Descripción                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Propietario del perfil de facturación        | Administrar todo para un perfil de facturación                                          |
| Colaborador de perfiles de facturación  | Administrar todo excepto los permisos en un perfil de facturación                        |
| Lector de perfiles de facturación       | Vista de solo lectura de todo en un perfil de facturación                                |
| Administrador de facturas              | Ver y pagar facturas y tiene una vista de solo lectura de todo en un perfil de facturación  |

## <a name="view-billing-profiles"></a>Ver perfiles de facturación

1. En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.
2. Elija **Perfiles de facturación** y, a continuación, elija un perfil de facturación de la lista.

    - En la **pestaña Información** general, puede editar los detalles del perfil de facturación y activar o desactivar el envío de una factura por correo electrónico.
    - En la **pestaña Permisos,** puede asignar roles a los usuarios para pagar facturas.
    - En la **pestaña Saldo de crédito de Azure,** los clientes de Azure pueden ver el historial de saldos de transacciones para los créditos de Azure usados por ese perfil de facturación.
    - En la **pestaña Créditos de Azure,** los clientes de Azure pueden ver una lista de créditos de Azure asociados con ese perfil de facturación y sus fechas de expiración.

    > [!NOTE]
    > Si no tiene créditos de Azure, no verá las pestañas Saldo de crédito de **Azure** o **Créditos de Azure.**

## <a name="need-help-contact-support"></a>¿Necesita ayuda? Contactar soporte

Si tiene preguntas o necesita ayuda con los cargos de Azure, cree una solicitud de soporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">técnico con soporte técnico de Azure</a>.

Si tiene preguntas o necesita ayuda con su perfil de facturación en el Centro de administración de Microsoft 365, póngase en contacto con el soporte [técnico para productos empresariales](../../business-video/get-help-support.md).
