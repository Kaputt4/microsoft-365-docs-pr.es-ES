---
title: Administrar cuentas de facturación
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre las cuentas de facturación y cómo administrarlas.
ms.openlocfilehash: 2382396c348fab0b24a269e9678193041ac2c19e
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032638"
---
# <a name="manage-billing-accounts"></a>Administrar cuentas de facturación

Se crea una cuenta de facturación cuando te registras para probar o comprar productos de Microsoft. Usas tu cuenta de facturación para administrar la configuración de tu cuenta, las facturas, los métodos de pago y las compras. Puede tener acceso a varias cuentas de facturación. Por ejemplo, se suscribió a Microsoft 365 directamente o tiene acceso al contrato de Contrato Enterprise, el Contrato de servicios de productos & de Microsoft o el Contrato de cliente de Microsoft de su organización. Para cada uno de estos escenarios, tendrías una cuenta de facturación independiente.

El Centro de administración de Microsoft 365 admite actualmente el siguiente tipo de cuentas de facturación:

- Microsoft Online Services: esta cuenta de facturación se crea al registrarse para obtener una suscripción a Microsoft 365 directamente.
- Programa contrato de & de productos de Microsoft (MPSA): esta cuenta de facturación se crea cuando su organización firma un contrato de licencias por volumen de MPSA para comprar software y servicios en línea.
- Contrato de cliente de Microsoft: esta cuenta de facturación se crea cuando su organización trabaja con un representante de Microsoft, un partner autorizado o compra de forma independiente.

La <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">página Cuentas de</a> facturación proporciona una vista de sus cuentas comerciales con Microsoft. De forma predeterminada, la organización tiene al menos una cuenta de facturación asociada a un contrato que se acepta en el momento de la compra directa o mediante un acuerdo de licencias por volumen.

## <a name="understand-billing-account-details"></a>Comprender los detalles de la cuenta de facturación

La parte superior de la página **de detalles de** cuentas de facturación es su perfil de cuenta y contiene información legal y fiscal sobre su organización. Puede actualizar su perfil para cambiar la dirección legal y el número de teléfono. Esta cuenta es la entidad legal que paga los productos que compra.

En la tabla siguiente se enumeran los términos importantes que se muestran en la página de detalles **de cuentas de** facturación.

| Nombre del campo | Descripción |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dirección vendida | La entidad jurídica responsable del pago e identificada en la factura. La dirección proporcionada aquí se usa para determinar la tasa de impuestos, a menos que opte por proporcionar una dirección de envío alternativa durante la compra. Para obtener más información, consulte [Información sobre impuestos](billing-and-payments/tax-information.md). |
| Segmento | Un campo de solo lectura que identifica el segmento empresarial de su organización (comercial, educativo, gubernamental o sin ánimo de lucro). |
| Estado de la cuenta | Un campo de solo lectura que especifica el estado de su cuenta comercial con Microsoft. |
| Id. de impuestos | Si está fuera de los Estados Unidos, debe proporcionar un IVA o equivalente local. Para obtener más información, consulte [Información sobre impuestos](billing-and-payments/tax-information.md). |
| Acuerdo | Cuando se crea una cuenta de facturación, ya sea mediante una compra directa o un acuerdo de licencias por volumen, una organización acepta o firma un acuerdo que describe los términos & condiciones de la cuenta. Si procede, esta vista muestra un historial de acuerdos. Si tiene que aceptar términos actualizados, se muestra un vínculo para **Aprobar** acuerdo. |
| Perfiles de facturación | Un perfil de facturación define las propiedades de la factura, como quién recibe la factura, cómo se entrega la factura, los términos de pago y un número de pedido de compra. Para distribuir la facturación en toda la organización, puede crear varios perfiles de facturación e identificar el perfil de facturación adecuado en el momento de la compra. Para obtener más información sobre los perfiles de facturación y cómo puede usarlos para crear opciones de facturación más flexibles para su organización, [administre los perfiles de facturación.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> Si desea cambiar  el nombre o la dirección de venta, pero no ve un vínculo Editar, debe ponerse en contacto con el soporte técnico [para](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) cambiarlo.  Las solicitudes para un cambio **de nombre** vendido requerirán una comprobación de crédito. Esté preparado para compartir uno de los siguientes documentos con Microsoft cuando se pondrá en contacto con el soporte técnico: 
>
> - Documento emitido por el gobierno o carta de registro
> - Imprimir en el registro de la empresa local
>
> El soporte técnico puede ayudar con los cambios de nombre y dirección en los que solo cambia el nombre del cliente, pero la entidad sigue siendo la misma. La documentación proporcionada debe mostrar claramente que solo ha cambiado el nombre de la entidad. Si el cambio es el resultado de una transacción, incluida la venta de negocios, un cambio de controles o una desinstición o "spinoff" de una filial de cliente, ponte en contacto con el vendedor de Microsoft.

## <a name="shipping-addresses"></a>Direcciones de envío

En esta sección se enumeran las direcciones de envío asociadas a tu cuenta de facturación. Cuando realices una compra, puedes usar esta dirección para identificar dónde se envía o se usa la compra. La dirección de envío es editable. Puede agregar una dirección de envío o actualizar la dirección existente. Esta dirección se usa para determinar la tasa de impuestos de la compra.

## <a name="understand-access-to-billing-accounts"></a>Comprender el acceso a las cuentas de facturación

Puede proporcionar a otros usuarios acceso a la cuenta de facturación en el Centro de administración de Microsoft 365 a través de roles y permisos. Solo el propietario de una cuenta de facturación puede conceder acceso a una cuenta de facturación. Puede asignar uno de los siguientes roles a los usuarios:

- **Propietario de la cuenta de facturación** &mdash; Puede asignar permisos, editar cuentas, firmar acuerdos y ver cuentas.
- **Colaborador de cuenta de facturación** &mdash; Puede editar cuentas, firmar acuerdos y ver cuentas.
- **Lector de cuentas de facturación** &mdash; Puede ver cuentas.

> [!Note]
> Los roles de cuenta de facturación solo se aplican a cuentas de facturación y no se aplican a otros escenarios del Centro de administración de Microsoft 365.

## <a name="related-articles"></a>Artículos relacionados

[Información de impuestos](billing-and-payments/tax-information.md)

[Administrar perfiles de facturación](billing-and-payments/manage-billing-profiles.md)
