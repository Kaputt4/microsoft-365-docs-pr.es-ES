---
title: Administrar cuentas de facturación
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.openlocfilehash: 87cc861ab48b99106a3cbd50d8ded91205ffb0a2
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402611"
---
# <a name="manage-billing-accounts"></a>Administrar cuentas de facturación

Se crea una cuenta de facturación cuando se registra para probar o comprar productos de Microsoft. Use su cuenta de facturación para administrar la configuración de la cuenta, las facturas, los métodos de pago y las compras. Puede tener acceso a varias cuentas de facturación. Por ejemplo, se registró en Microsoft 365 directamente o tiene acceso al contrato Enterprise de la organización, el contrato de servicios & de productos de Microsoft o el contrato de cliente de Microsoft. Para cada uno de estos escenarios, tendría una cuenta de facturación independiente.

Actualmente, el centro de administración de Microsoft 365 es compatible con el siguiente tipo de cuentas de facturación:

- Programa de Microsoft Online Services: esta cuenta de facturación se crea al registrarse para obtener una suscripción a Microsoft 365 directamente.
- Programa Products & Services Agreement (MPSA) de Microsoft: esta cuenta de facturación se crea cuando la organización firma un contrato de licencia por volumen de MPSA para comprar software y servicios en línea.
- Contrato de cliente de Microsoft: esta cuenta de facturación se crea cuando la organización trabaja con un representante de Microsoft, un socio autorizado o con compras por separado.

La página <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">cuentas de facturación</a> proporciona una vista de las cuentas comerciales con Microsoft. De forma predeterminada, su organización tiene al menos una cuenta de facturación asociada con un acuerdo que se acepta en el momento de una compra directa o a través de un acuerdo de licencias por volumen.

## <a name="understand-billing-account-details"></a>Descripción de los detalles de la cuenta de facturación

La parte superior de la página de detalles de **las cuentas de facturación** es su perfil de cuenta y contiene información legal y fiscal sobre la organización. Puede actualizar su perfil para cambiar su dirección jurídica y su número de teléfono. Esta cuenta es la entidad jurídica que paga los productos que compra.

En la siguiente tabla se enumeran los términos importantes que aparecen en la página de detalles de **cuentas de facturación** .

| Nombre del campo | Description |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dirección de ventas | La entidad jurídica responsable del pago e identificada en la factura. La dirección que se proporciona aquí se usa para determinar la tasa de impuestos a menos que opte por proporcionar una dirección de envío alternativa durante la compra. Para obtener más información, consulte [información fiscal](billing-and-payments/tax-information.md). |
| Sector | Un campo de solo lectura que identifica el segmento empresarial de la organización (comercial, educativa, gubernamental o sin ánimo de lucro). |
| Estado de la cuenta | Un campo de solo lectura que especifica el estado de su cuenta comercial con Microsoft. |
| IDENTIFICADOR de impuesto | Si está fuera de los Estados Unidos, debe proporcionar un IVA o un equivalente local. Para obtener más información, consulte [información fiscal](billing-and-payments/tax-information.md). |
| Agreement | Cuando se crea una cuenta de facturación, ya sea a través de una compra directa o un acuerdo de licencias por volumen, un signatario de la organización acepta, o firma, un acuerdo que describe los términos & condiciones de la cuenta. Si procede, esta vista muestra el historial de un contrato. Si se le pide que acepte los términos actualizados, se muestra un vínculo para el **acuerdo de aprobación** . |
| Perfiles de facturación | Un perfil de facturación define las propiedades de la factura, como quién recibe la factura, cómo se entrega la factura, las condiciones de pago y un número de pedido de compra. Para distribuir la facturación en su organización, puede crear varios perfiles de facturación e identificar el perfil de facturación adecuado en el momento de la compra. Para obtener más información acerca de los perfiles de facturación y de cómo puede usarlos para crear opciones de facturación más flexibles para su organización, [administre los perfiles de facturación](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Si desea cambiar el nombre o la dirección del **usuario al** que se ha vendido, pero no ve ningún vínculo **Editar** , debe [ponerse en contacto con el soporte técnico](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) para cambiarlo. Las solicitudes de un cambio de nombre **vendido** requerirán una comprobación de crédito. Cuando se ponga en contacto con el soporte técnico, tenga preparado uno de los siguientes documentos:
>
> - Documento de anuncio externo que indica cualquier cambio en el nombre de la compañía o la estructura corporativa
> - Documento o carta de registro emitido por el gobierno
> - Imprimir fuera del registro de la compañía local
>
> El soporte técnico puede ayudarle con los cambios de nombre y dirección donde solo cambia el nombre del cliente, pero la entidad sigue siendo la misma. La documentación proporcionada debería indicar claramente que solo ha cambiado el nombre de la entidad. Si el cambio está relacionado con cualquier transacción, como una venta de negocio o un desinversión o "spinoff" de una filial de un cliente, ponte en contacto con el vendedor de Microsoft.

## <a name="shipping-addresses"></a>Direcciones de envío

En esta sección se enumeran las direcciones de envío asociadas a su cuenta de facturación. Al realizar una compra, puede usar esta dirección para identificar dónde se ha enviado o usado la compra. La dirección de envío se puede editar. Puede Agregar una dirección de envío o actualizar la dirección existente. Esta dirección se usa para determinar el tipo impositivo de la compra.

## <a name="understand-access-to-billing-accounts"></a>Comprender el acceso a las cuentas de facturación

Puede proporcionar a otros usuarios acceso a la cuenta de facturación en el centro de administración de Microsoft 365 mediante roles y permisos. Solo un propietario de la cuenta de facturación puede conceder acceso a una cuenta de facturación. Puede asignar uno de los siguientes roles a los usuarios:

- Propietario de la **cuenta de facturación** &mdash; Puede asignar permisos, editar cuentas, firmar contratos y ver cuentas.
- Colaborador de cuenta de **facturación** &mdash; Puede editar cuentas, firmar contratos y ver cuentas.
- Lector de cuentas de **facturación** &mdash; Permite ver cuentas.

> [!Note]
> Los roles de la cuenta de facturación solo se aplican a las cuentas de facturación y no se aplican a otros escenarios del centro de administración de Microsoft 365.

## <a name="related-articles"></a>Artículos relacionados

[Información de impuestos](billing-and-payments/tax-information.md)

[Administrar perfiles de facturación](billing-and-payments/manage-billing-profiles.md)