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
ms.openlocfilehash: c2cf7584148bb846541328396885d20c00e2712a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911427"
---
# <a name="manage-billing-accounts"></a>Administrar cuentas de facturación

Se crea una cuenta de facturación cuando se registra para probar o comprar productos de Microsoft. Usas tu cuenta de facturación para administrar la configuración de la cuenta, las facturas, los métodos de pago y las compras. Puedes tener acceso a varias cuentas de facturación. Por ejemplo, se inscribió en Microsoft 365 directamente o tiene acceso al contrato de Contrato Enterprise de productos de Microsoft, al Contrato de servicios de & de Microsoft o al contrato de cliente de Microsoft. Para cada uno de estos escenarios, tendrías una cuenta de facturación independiente.

El Centro de administración de Microsoft 365 admite actualmente el siguiente tipo de cuentas de facturación:

- Microsoft Online Services: esta cuenta de facturación se crea al registrarse para una suscripción a Microsoft 365 directamente.
- Programa contrato de & de servicios de Microsoft Products (MPSA): esta cuenta de facturación se crea cuando su organización firma un contrato de licencias por volumen de MPSA para comprar software y servicios en línea.
- Contrato de cliente de Microsoft: esta cuenta de facturación se crea cuando la organización trabaja con un representante de Microsoft, un partner autorizado o compras de forma independiente.

La <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">página Cuentas de</a> facturación proporciona una vista de sus cuentas comerciales con Microsoft. De forma predeterminada, su organización tiene al menos una cuenta de facturación asociada a un contrato que se acepta en el momento de una compra directa o mediante un acuerdo de licencias por volumen.

## <a name="understand-billing-account-details"></a>Comprender los detalles de la cuenta de facturación

La parte superior de la **página de** detalles cuentas de facturación es su perfil de cuenta y contiene información legal y fiscal sobre su organización. Puedes actualizar tu perfil para cambiar la dirección legal y el número de teléfono. Esta cuenta es la entidad jurídica que paga los productos que compra.

En la tabla siguiente se enumeran los términos importantes que se ven en la página de detalles **cuentas de** facturación.

| Nombre del campo | Descripción |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dirección vendida | La entidad jurídica responsable del pago e identificada en la factura. La dirección proporcionada aquí se usa para determinar la tasa de impuestos, a menos que opte por proporcionar una dirección de envío alternativa durante la compra. Para obtener más información, consulte [Información sobre impuestos](billing-and-payments/tax-information.md). |
| Segmento | Un campo de solo lectura que identifica el segmento de negocio de su organización (Comercial, Educativo, Gubernamental o Sin ánimo de lucro). |
| Estado de la cuenta | Campo de solo lectura que especifica el estado de su cuenta comercial con Microsoft. |
| Id. de impuestos | Si está fuera de los Estados Unidos, debe proporcionar un IVA o equivalente local. Para obtener más información, consulte [Información sobre impuestos](billing-and-payments/tax-information.md). |
| Acuerdo | Cuando se crea una cuenta de facturación, ya sea mediante una compra directa o un acuerdo de licencias por volumen, un firmante de la organización acepta o firma un acuerdo que describe los términos & condiciones de la cuenta. Si procede, esta vista enumera un historial de acuerdos. Si tienes que aceptar términos actualizados, se muestra un vínculo para **Aprobar** acuerdo. |
| Perfiles de facturación | Un perfil de facturación define las propiedades de la factura, como quién recibe la factura, cómo se entrega la factura, los términos de pago y un número de pedido. Para distribuir la facturación en toda la organización, puede crear varios perfiles de facturación e identificar el perfil de facturación adecuado en el momento de la compra. Para obtener más información sobre los perfiles de facturación y cómo usarlos para crear opciones de facturación más flexibles para su organización, comprenda los perfiles [de facturación](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Si necesita cambiar el **nombre** o la dirección vendidos, pero no ve un vínculo **Editar,** debe ponerse en contacto con el soporte técnico [para](../admin/contact-support-for-business-products.md) cambiarlo. Las solicitudes para un cambio **de nombre** vendido requerirán una comprobación de crédito. Complete [este formulario](https://www.microsoft.com/download/details.aspx?id=102732)y esté listo para compartir uno de los siguientes documentos con Microsoft al ponerse en contacto con el soporte técnico:
>
> - Documento emitido por el gobierno o carta de registro
> - Imprimir del registro de la empresa local
>
> La compatibilidad puede ayudar con los cambios de nombre y dirección en los que solo cambia el nombre del cliente, pero la entidad sigue siendo la misma. La documentación proporcionada debe mostrar claramente que solo ha cambiado el nombre de la entidad. Si el cambio es el resultado de una transacción, incluida la venta de negocios, un cambio de controles o una desinstición o "spinoff" de una filial de cliente, póngase en contacto con su vendedor de Microsoft.

## <a name="shipping-addresses"></a>Direcciones de envío

En esta sección se enumeran las direcciones de envío asociadas con su cuenta de facturación. Al realizar una compra, puedes usar esta dirección para identificar dónde se envía o usa la compra. La dirección de envío es editable. Puede agregar una dirección de envío o actualizar la dirección existente. Esta dirección se usa para determinar la tasa fiscal de la compra.

## <a name="understand-access-to-billing-accounts"></a>Comprender el acceso a cuentas de facturación

Puede proporcionar a otros usuarios acceso a la cuenta de facturación en el Centro de administración de Microsoft 365 a través de roles y permisos. Solo el propietario de una cuenta de facturación puede conceder acceso a una cuenta de facturación. Puede asignar uno de los siguientes roles a los usuarios:

- **Propietario de la cuenta de facturación** &mdash; Puede asignar permisos, editar cuentas, firmar acuerdos y ver cuentas.
- **Colaborador de cuenta de facturación** &mdash; Puede editar cuentas, firmar acuerdos y ver cuentas.
- **Lector de cuentas de facturación** &mdash; Puede ver cuentas.

> [!Note]
> Los roles de cuenta de facturación solo se aplican a cuentas de facturación y no se aplican a otros escenarios del Centro de administración de Microsoft 365.

## <a name="related-content"></a>Contenido relacionado

[Información fiscal](billing-and-payments/tax-information.md) (artículo) \
[Comprender los perfiles de facturación](billing-and-payments/manage-billing-profiles.md) (artículo)