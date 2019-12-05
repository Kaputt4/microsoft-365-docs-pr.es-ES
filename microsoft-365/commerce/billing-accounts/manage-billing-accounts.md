---
title: Administrar cuentas de facturación
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Obtenga información sobre las cuentas de facturación y cómo administrarlas.
ms.openlocfilehash: 9ea96a0187a1f4bec9c71dc02478375a4c13b371
ms.sourcegitcommit: 95a07b328166f637a481c8b5c53669eaf8ff0db8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "39837971"
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

| Nombre del campo | Descripción |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dirección de ventas | La entidad jurídica responsable del pago e identificada en la factura. La dirección que se proporciona aquí se usa para determinar la tasa de impuestos a menos que opte por proporcionar una dirección de envío alternativa durante la compra. Para obtener más información, consulte [información fiscal](#tax-information). |
| Sector | Un campo de solo lectura que identifica el segmento empresarial de la organización (comercial, educativa, gubernamental o sin ánimo de lucro). |
| Estado de la cuenta | Un campo de solo lectura que especifica el estado de su cuenta comercial con Microsoft. |
| IDENTIFICADOR de impuesto | Si está fuera de los Estados Unidos, debe proporcionar un IVA o un equivalente local. Para obtener más información, consulte [información fiscal](#tax-information). |
| Agreement | Cuando se crea una cuenta de facturación, ya sea a través de una compra directa o un acuerdo de licencias por volumen, un signatario de la organización acepta, o firma, un acuerdo que describe los términos & condiciones de la cuenta. Si procede, esta vista muestra el historial de un contrato. Si se le pide que acepte los términos actualizados, se muestra un vínculo para el **acuerdo de aprobación** . |
| Perfiles de facturación | Un perfil de facturación define las propiedades de la factura, como quién recibe la factura, cómo se entrega la factura, las condiciones de pago y un número de pedido de compra. Para distribuir la facturación en su organización, puede crear varios perfiles de facturación e identificar el perfil de facturación adecuado en el momento de la compra. Para obtener más información acerca de los perfiles de facturación y de cómo puede usarlos para crear opciones de facturación más flexibles para su organización, [administre los perfiles de facturación](../billing-and-payments/manage-billing-profiles.md). |

## <a name="shipping-addresses"></a>Direcciones de envío

En esta sección se enumeran las direcciones de envío asociadas a su cuenta de facturación. Al realizar una compra, puede usar esta dirección para identificar dónde se ha enviado o usado la compra. La dirección de envío se puede editar. Puede Agregar una dirección de envío o actualizar la dirección existente. Esta dirección se usa para determinar el tipo impositivo de la compra.

## <a name="understand-access-to-billing-accounts"></a>Comprender el acceso a las cuentas de facturación

Puede proporcionar a otros usuarios acceso a la cuenta de facturación en el centro de administración de Microsoft 365 mediante roles y permisos. Solo un propietario de la cuenta de facturación puede conceder acceso a una cuenta de facturación. Puede asignar uno de los siguientes roles a los usuarios:

- El **propietario** &mdash; de la cuenta de facturación puede asignar permisos, editar cuentas, firmar contratos y ver cuentas.
- El **colaborador** &mdash; de la cuenta de facturación puede editar cuentas, firmar contratos y ver cuentas.
- El **lector** &mdash; de la cuenta de facturación puede ver cuentas.

> [!Note]
> Los roles de la cuenta de facturación solo se aplican a las cuentas de facturación y no se aplican a otros escenarios del centro de administración de Microsoft 365.

## <a name="tax-information"></a>Información fiscal

Los impuestos de las compras del centro de administración de Microsoft 365 que realiza a través de Microsoft vienen determinados por la dirección de la empresa o, si es diferente, por su dirección de envío. Si está en los Estados Unidos, debe proporcionar un número de identificación de empleador federal (FEIN).

Las empresas de estos países pueden proporcionar su número de IVA:

:::row:::
    :::column:::
- Austria
- Bélgica
- Bulgaria
- Croacia
- Chipre
- Chequia
- Dinamarca
- Estonia
- Finlandia
- Francia
- Alemania
- Grecia
- Hungría
- Irlanda
- Italia
- Letonia
    :::column-end:::
    :::column:::
- Liechtenstein
- Lituania
- Luxemburgo
- Malta
- Mónaco
- Países Bajos
- Noruega
- Polonia
- Portugal
- Rumania
- Eslovaquia
- Sudáfrica
- España
- Suecia
- Suiza
- Reino Unido
    :::column-end:::
:::row-end:::

Estos países pueden proporcionar su número de IVA o equivalente local en su información de cuenta de facturación.

|Márketing| Identificador de impuestos |
|------|----------------|
| Australia | ABN (opcional) |
| Brasil | CNPJ (obligatorio) |
| India | GSTIN (opcional), ID de PAN (obligatorio) |
| Isla de Man | NIF (opcional) |
| JPRatingExplicitAllowed | Número de registro de GST (opcional) |
| Mónaco | NIF (opcional) |
| Taiwán | NIF (opcional) |

> [!Note]
> Si necesita ponerse en contacto con el soporte técnico, tenga el FEIN, el número de IVA o el equivalente local listo para dar al agente de soporte.

## <a name="tax-exempt-status"></a>Estado de exención de impuestos

Si califica para el estado de exento de impuestos en su mercado, [inicie una solicitud de servicio](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) para establecer el estado de exención de impuestos para su organización.

Prepare la siguiente documentación:

|País o configuración regional | Documentación |
|------------------|----------------|
| Estados Unidos | Certificado de exención de impuestos de ventas |
| Canadá | Certificado de exención (o letra de autorización equivalente) |
| Irlanda | Certificado de exención de impuestos de 13B/56A|
| Organizaciones internacionales que mantienen la exención de impuestos | Confirmación de certificación/carta de las autoridades fiscales locales |
| Puerto Rico | Certificado de compra exentas |

## <a name="calculate-taxes"></a>Calcular impuestos

Los impuestos se calculan con relación al precio unitario y, a continuación, se agregan.

Por ejemplo:

>*(precio unitario X tasa de impuestos) X cantidad = total de impuesto sobre las ventas*

O bien,

>($1,29 X 0,095) X 100 = $12,25