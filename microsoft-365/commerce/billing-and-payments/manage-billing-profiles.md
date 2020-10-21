---
title: Administrar perfiles de facturación
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre cómo los perfiles de facturación admiten facturas.
keywords: Perfil de facturación, facturas, cargos, cargos administrados
ms.openlocfilehash: de6d6cd65d9e83e7211bcdc33f1774aaec3d1729
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638452"
---
# <a name="manage-billing-profiles"></a>Administrar perfiles de facturación

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Para los clientes comerciales que compran productos y servicios de Microsoft, los perfiles de facturación le permiten personalizar los elementos que se incluyen en la factura y cómo pagar sus facturas.

Los perfiles de facturación incluyen la siguiente información:

- **Cuenta** &ndash; de facturación Nombre de la cuenta de facturación con la que está relacionado el perfil
- **Métodos** &ndash; de pago Tarjetas de crédito o débito, cuentas bancarias, cheque o transferencia bancaria
- **Información** &ndash; de contacto Dirección de facturación y nombre de contacto
- Configuración de la **factura** &ndash; Divisa basada en el país de la cuenta de facturación, un número de pedido de compra opcional y la opción de recibir facturas como datos adjuntos de correo electrónico
- **Permisos** &ndash; Permisos que permiten cambiar el perfil de facturación, pagar facturas o usar el método de pago en el perfil de facturación para realizar compras

Use perfiles de facturación para controlar las compras y personalizar la factura. Se genera una factura mensual para los productos comprados con el perfil de facturación. Puede personalizar la factura como actualizar el número de pedido de compra y la preferencia de factura de correo electrónico.

Durante la primera compra, se creará automáticamente un perfil de facturación para la cuenta de facturación. Puede crear perfiles de facturación en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfiles de facturación</a> para configurar más facturas. Por ejemplo, puede usar diferentes perfiles de facturación al realizar compras para cada departamento de su organización. En la próxima fecha de facturación, recibirá una factura para cada perfil de facturación.

## <a name="billing-profile-roles"></a>Roles de Perfil de facturación

Los roles en perfiles de facturación tienen permisos para controlar las compras y ver y administrar las facturas. Asigne estos roles a los usuarios que realizan un seguimiento, organizan y pagan facturas, como los miembros del equipo de compras de su organización.

| Role                          | Descripción                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Propietario del perfil de facturación         | Administrar todo para un perfil de facturación                                           |
| Colaborador de Perfil de facturación   | Administrar todo excepto permisos en un perfil de facturación                         |
| Lector de perfiles de facturación        | Vista de solo lectura de todo en un perfil de facturación                                 |
| Administrador de facturas               | Ver y pagar facturas y tiene una vista de solo lectura de todo en un perfil de facturación   |

## <a name="view-billing-profiles"></a>Ver perfiles de facturación

1. En el Centro de administración, vaya a la página **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.

2. Elija **perfiles de facturación**y, después, elija un perfil de facturación de la lista.

    - En la ficha **información general** , puede editar los detalles del perfil de facturación y activar o desactivar el envío de facturas por correo electrónico.

    - En la pestaña **permisos** , puede asignar roles a los usuarios para pagar facturas.

    - En la pestaña **saldo de crédito de Azure** , los clientes de Azure pueden ver el historial de saldo de transacciones para los créditos de Azure usados por ese perfil de facturación.

    - En la pestaña **Azure créditos** , los clientes de Azure pueden ver una lista de créditos de Azure asociados con ese perfil de facturación y sus fechas de expiración.

    > [!NOTE]
    > Si no tiene ningún crédito de Azure, no podrá ver las pestañas de **saldo haber** de Azure o **créditos de Azure** .

## <a name="need-help-contact-support"></a>¿Necesita ayuda? Póngase en contacto con el servicio de soporte técnico.

Si tiene preguntas o necesita ayuda con los cargos de Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">cree una solicitud de soporte técnico con el soporte de Azure</a>.

Si tiene alguna pregunta o necesita ayuda con su perfil de facturación en el centro de administración de Microsoft 365, [póngase en contacto con soporte técnico para productos empresariales](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
