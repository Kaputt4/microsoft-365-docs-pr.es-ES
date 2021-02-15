---
title: Entender los perfiles de facturación
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- Commerce
search.appverid:
- MET150
description: Obtenga información sobre cómo los perfiles de facturación admiten las facturas.
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667782"
---
# <a name="understand-billing-profiles"></a>Entender los perfiles de facturación

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Para los clientes comerciales que compran productos y servicios de Microsoft, los perfiles de facturación permiten personalizar los elementos que se incluyen en la factura y cómo pagar las facturas.

Los perfiles de facturación incluyen la siguiente información:

- **Cuenta de facturación** &ndash; Nombre de la cuenta de facturación con la que está relacionado el perfil
- **Métodos de pago** &ndash; Tarjetas de crédito o débito, cuentas bancarias, cheque o transferencia bancaria
- **Información de contacto** &ndash; Dirección de facturación y un nombre de contacto
- **Configuración de factura** &ndash; Moneda basada en el país de la cuenta de facturación, un número de pedido de compra opcional y la opción de recibir facturas como datos adjuntos de correo electrónico
- **Permisos** &ndash; Permisos que le permiten cambiar el perfil de facturación, pagar facturas o usar el método de pago en el perfil de facturación para realizar compras

Usa perfiles de facturación para controlar tus compras y personalizar la factura. Se genera una factura mensual para los productos comprados con el perfil de facturación. Puede personalizar la factura, como actualizar el número de pedido de compra y la preferencia de factura de correo electrónico.

Durante la primera compra, se crea automáticamente un perfil de facturación para tu cuenta de facturación. Puede crear perfiles de facturación en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfiles de facturación</a> para configurar más facturas. Por ejemplo, puedes usar diferentes perfiles de facturación al realizar compras para cada departamento de la organización. En la próxima fecha de facturación, recibirás una factura para cada perfil de facturación.

## <a name="billing-profile-roles"></a>Roles de perfil de facturación

Los roles de los perfiles de facturación tienen permisos para controlar las compras y ver y administrar facturas. Asigne estos roles a los usuarios que realicen un seguimiento, organicen y paguen facturas, como los miembros del equipo de adquisiciones de su organización.

| Función                          | Descripción                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Propietario del perfil de facturación         | Administrar todo para un perfil de facturación                                           |
| Colaborador de perfil de facturación   | Administrar todo excepto los permisos en un perfil de facturación                         |
| Lector de perfiles de facturación        | Vista de solo lectura de todo en un perfil de facturación                                 |
| Administrador de facturas               | Ver y pagar facturas, y tiene una vista de solo lectura de todo en un perfil de facturación   |

## <a name="view-billing-profiles"></a>Ver perfiles de facturación

1. En el Centro de administración, vaya a la página **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.

2. Elija **Perfiles de facturación** y, a continuación, elija un perfil de facturación de la lista.

    - En la **pestaña Información** general, puede editar los detalles del perfil de facturación y activar o desactivar el envío de una factura por correo electrónico.

    - En la **pestaña Permisos,** puede asignar roles a los usuarios para pagar facturas.

    - En la pestaña **Saldo de crédito de Azure,** los clientes de Azure pueden ver el historial de saldos de transacciones para los créditos de Azure usados por ese perfil de facturación.

    - En la **pestaña Créditos** de Azure, los clientes de Azure pueden ver una lista de créditos de Azure asociados con ese perfil de facturación y sus fechas de expiración.

    > [!NOTE]
    > Si no tiene créditos de Azure, no verá el saldo de crédito de **Azure** ni las pestañas créditos de **Azure.**

## <a name="need-help-contact-support"></a>¿Necesita ayuda? Póngase en contacto con el servicio de soporte técnico.

Si tiene preguntas o necesita ayuda con los cargos de Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">cree una solicitud de soporte técnico con el soporte técnico de Azure.</a>

Si tiene preguntas o necesita ayuda con su perfil de facturación en el Centro de administración de Microsoft 365, póngase en contacto con el soporte [técnico para productos empresariales.](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)
