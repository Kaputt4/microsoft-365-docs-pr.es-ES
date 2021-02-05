---
title: Entender su factura o recibo
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
description: Obtenga información acerca de cómo leer y comprender su factura o recibo de productos empresariales de Microsoft.
keywords: cuentas de facturación, información de la organización, facturas
ms.openlocfilehash: 79702c369a097dbcbc8fe2319cd04663f9fe0441
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114782"
---
# <a name="understand-your-bill-or-invoice"></a>Entender su factura o recibo

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

La factura le proporciona un resumen de los cargos y las instrucciones de pago. Puede [ver su factura en línea](#view-your-online-invoice) en el Centro de administración de Microsoft 365. También puede descargarla en Portable Document Format (.pdf) para enviarla por correo electrónico.

Si solo tiene una suscripción a Microsoft 365, consulte [Comprender su factura o recibo de Microsoft 365 para empresas](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Comprender el encabezado de la factura

En la parte superior de la primera página se identifica al usuario responsable del pago, la dirección a donde se envió la factura y un resumen de los gastos.

| Término | Descripción |
| --- | --- |
| Vendido a |La cuenta de facturación que identifica el nombre y la dirección de la entidad jurídica responsable del pago. Esta información puede administrarse en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Cuentas de facturación</a>, en donde encontrará el contrato de la cuenta y podrá administrar los roles y permisos. |
| Facturar a |Identifica quién recibe la factura. Esta información puede administrarse en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfiles de facturación</a>. El perfil de facturación también se muestra en la página de la factura en línea, en la sección **Resumen de la factura**. Para obtener más información sobre los perfiles de facturación y cómo puede usarlos para crear opciones de facturación más flexibles para su organización, consulte [Administrar perfiles de facturación](manage-billing-profiles.md). |
| Perfil de facturación |El nombre del perfil de facturación que se usa para definir las propiedades de la factura como **Factura para**, **Número de orden de compra** y condiciones de pago. Esta información puede administrarse en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfiles de facturación</a>. Para obtener más información acerca de los perfiles de facturación y cómo puede usarlos para crear opciones de facturación más flexibles para su organización, consulte [Administrar perfiles de facturación](manage-billing-profiles.md). |
| Número de factura |Número de factura único generado por Microsoft que se usa para hacer seguimiento. |
| Fecha de la factura |Fecha en que se genera la factura, normalmente de cinco a 12 días después de que finaliza el ciclo de facturación. Puede comprobar la fecha de su factura en la página de detalles del perfil de facturación. Las cargos que se generen entre el final del período de facturación y la fecha de la factura serán incluidos en la factura del mes siguiente, ya que forman parte del siguiente período de facturación. Las fechas de inicio y finalización del período de facturación de cada factura se muestran en la versión en PDF en el **Resumen de facturación**.|
| Términos de pago |La forma en la que paga su factura de Microsoft. *30 días netos* significa que usted paga de acuerdo con las instrucciones de la factura, en un plazo de 30 días desde la fecha de facturación. |

## <a name="understand-the-billing-summary"></a>Entender el resumen de facturación

El **Resumen de facturación** muestra el resumen de los cargos desde el período de facturación anterior, los créditos aplicados, los impuestos y el monto total pendiente por pagar.

| Término | Descripción |
| --- | --- |
| Cargos|El número total de productos comprados para este periodo de facturación con sus impuestos y tarifas correspondientes. Las compras se suman para ofrecer una vista concisa de la factura. |
| Créditos |Créditos recibidos por devoluciones |
| Créditos de Azure aplicados |Los créditos de Azure que se aplican automáticamente a los cargos de Azure en cada período de facturación. Si no tiene ningún crédito de Azure, este campo permanece oculto. Para obtener más información sobre los créditos de Azure, consulte [Realizar seguimiento del saldo crediticio de Azure del Contrato de cliente de Microsoft](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotal |El monto adeudado antes de los impuestos |
| Impuestos |El tipo y la cantidad de impuestos que paga de acuerdo con el país del perfil de facturación. Si no tiene que pagar impuestos, no se mostrará ningún impuesto en la factura. |

### <a name="understand-your-charges"></a>Entender los cargos

Las páginas de los cargos muestran el costo desglosado por producto. Para los clientes de Azure, los cargos podrían estar organizados por sección de la factura. Para obtener más información sobre cómo se usan las secciones de la factura con los productos de Azure, consulte [Secciones de la factura](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) en [Introducción a su cuenta de facturación de Contrato de cliente de Microsoft](https://docs.microsoft.com/azure/billing/billing-mca-overview). En cada orden de producto, el costo se desglosa por familia de servicios.

| Término |Descripción |
| --- | --- |
| Precio unitario | El precio unitario en vigencia del servicio (en la moneda del precio) que se usa para calcular el cargo. Este precio es único para cada producto, familia de servicios, medidor y oferta. |
| Cant. | Cantidad comprada o consumida durante el período de facturación |
| Cargos/créditos | Importe neto de los cargos después de que se apliquen los créditos/reembolsos |
| Crédito de Azure | El monto de los créditos de Azure aplicado a los Cargos/créditos |
| Tasa de impuestos | Tasa de impuesto según el país |
| Importe del impuesto | Importe del impuesto aplicado al pedido de acuerdo con la tasa de impuesto |
| Total | El monto total a pagar por la compra |

La línea de detalles de los artículos varía en función del tipo de producto por el que se le está cobrando. Por ejemplo, para los productos de Azure, se muestra la cantidad de créditos de Azure aplicados. Los productos basados en el puesto muestran un precio unitario y una cantidad. Los detalles de la factura muestran los productos comprados, los descuentos o los créditos aplicados, la tasa de impuestos y el monto, y los totales de la línea de artículos.

> Total = Cargos - Crédito de Azure + Impuestos

El monto total adeudado por cada familia de servicios se calcula al restar los créditos de Azure de los créditos/cargos y sumar los impuestos:

> Total = Cargos/créditos - Crédito de Azure + impuestos

Si hay cargos de Azure en su factura de los cuales desea obtener más información, consulte [Revisar la factura del Contrato de cliente de Microsoft](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Entender la última página de la factura

### <a name="payment-instructions"></a>Instrucciones de pago

En la parte inferior de la factura aparecen las instrucciones de cómo pagar su factura. Puede pagar por transferencia, cheque o en línea.

### <a name="publisher-information"></a>Información del publicador

Si en su factura aparecen otros servicios de terceros, se mostrarán el nombre y la dirección de cada publicador en la parte inferior de la factura.

## <a name="view-your-online-invoice"></a>Ver la factura en línea

Las facturas están disponibles en línea. Tiene a su disposición un vínculo para acceder a su factura en línea en su factura en PDF y en la notificación que recibe por correo electrónico. Puede expandir su factura en línea para ver más detalles de los cargos y de cada elemento. La factura en línea incluye:

- **Detalles de los precios**&mdash;Información adicional, incluidos los detalles sobre los descuentos y los precios de los productos.

- **Pago en línea**&mdash;Puede elegir realizar el pago en línea desde la factura.

- **Azure Cost Management**&mdash;Para los clientes de Azure, las facturas en línea incluyen un vínculo a Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>Para ver su factura en línea

1. En el Centro de administración, vaya a la página **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.

2. Para descargar la versión .pdf de su factura, elija **Descargar factura en PDF** en la fila de la factura que quiera ver.

3. Para ver su factura en línea, elija una factura de la lista. También puede descargar el archivo .pdf desde la página de detalles de la factura.

## <a name="invoice-faq"></a>Preguntas más frecuentes sobre su factura

### <a name="when-is-my-invoice-available"></a>¿Cuándo estará disponible mi factura?

Algunas facturas se generan en las 24 horas siguientes a la compra. Las demás facturas se generan al final del período de facturación e incluyen todos los elementos de ese período.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>¿Cómo puedo pagar el monto pendiente de mi factura?

Las instrucciones de pago dependen del método de pago y se muestran en la parte inferior del PDF de la factura. Si su método de pago es por tarjeta de crédito, se le cobrará automáticamente en un plazo de 10 días a partir de la fecha de la factura. Si su método de pago es por cheque o transferencia bancaria, consulte la información en **Instrucciones de pago** en el PDF.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>¿Cuál es la diferencia entre las direcciones de "Vendido a" y "Facturar a"?

- **Vendido a:** La entidad legal responsable del pago e identificada en la factura. La dirección proporcionada aquí se usa para determinar la tasa de impuestos, a menos que opte por proporcionar una dirección de envío alternativa durante la compra. Para obtener más información, consulte [Información sobre impuestos](tax-information.md).
- **Facturar a:** La dirección a la que se envía la factura física, si procede. Puede haber varias direcciones de **Facturar a** por cada entidad jurídica, pero solo habrá una dirección de **Facturar a** por cada perfil de facturación.

### <a name="what-are-billed-amount-and-amount-due"></a>¿Qué son el "Importe facturado" y el "Importe vencido?"

- **Importe facturado:** Monto total de la compra que ha realizado.
- **Importe vencido:** Saldo pendiente de lo que debe.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>¿Cuál es la diferencia entre el “Periodo de servicio" y el "Periodo de facturación"?

- **Período de servicio:** Período durante el cual se le cobrará por usar el servicio.
- **Período de facturación:** Período desde la última fecha de la factura.

### <a name="how-do-i-view-and-print-my-bill"></a>¿Cómo puedo ver e imprimir mi factura?

1. En la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>, seleccione un rango de fechas de la factura.
2. Para imprimir o guardar una copia en PDF de la factura, seleccione **Descargar factura PDF** y luego, imprima el archivo PDF.

Para obtener más información, consulte [Ver su factura o recibo](view-your-bill-or-invoice.md).

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>¿Por qué no veo el anticipo de Azure como método de pago?

El anticipo de Azure está disponible como método de pago solo para los productos y servicios de Azure elegibles.

## <a name="need-help-contact-support"></a>¿Necesita ayuda? Póngase en contacto con el servicio de soporte técnico.

Si tiene preguntas o necesita ayuda con los créditos de Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">cree una solicitud de soporte con el servicio de asistencia de Azure</a>.

Si tiene preguntas o necesita ayuda con su factura en el Centro de administración de Microsoft 365, [póngase en contacto con el servicio de asistencia para productos empresariales](../../admin/contact-support-for-business-products.md).