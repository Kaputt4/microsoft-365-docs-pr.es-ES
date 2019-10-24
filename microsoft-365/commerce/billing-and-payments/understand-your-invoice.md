---
title: Entender la factura
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Obtenga información sobre cómo leer y entender la factura de productos para empresas de Microsoft.
keywords: cuentas de facturación, información de la organización, facturas
ms.openlocfilehash: e0af9ec0808de97e55ef550c6feb51a146dbb5f6
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646462"
---
# <a name="understand-your-invoice"></a>Entender la factura

La factura proporciona un resumen de los cargos e instrucciones de pago. Puede [ver su factura en línea](#view-your-online-invoice) en el centro de administración de Microsoft 365. También puede descargarla en el formato de documento portátil (. pdf) para enviar por correo electrónico.

Si solo tiene una suscripción de Office 365, consulte [ver la factura de office 365 para empresas](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/view-your-bill-or-invoice).

## <a name="understand-the-invoice-header"></a>Descripción del encabezado de la factura

La parte superior de la primera página identifica quién es responsable del pago, a dónde se envía la factura y un resumen de los gastos.

| Term | Description |
| --- | --- |
| Vendido a |La cuenta de facturación que identifica el nombre y la dirección de la entidad jurídica responsable del pago. Esta información puede administrarse en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">cuentas de facturación</a> , donde puede encontrar el contrato de cuenta y administrar los roles y permisos. |
| Factura a |Identifica quién recibe la factura. Esta información puede administrarse en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfiles de facturación</a> . El perfil de facturación también se muestra en la página de facturas en línea, en la sección **Resumen de facturas** . Para obtener más información acerca de los perfiles de facturación y de cómo puede usarlos para crear opciones de facturación más flexibles para su organización, consulte [Manage Billing profiles](manage-billing-profiles.md). |
| Perfil de facturación |El nombre del perfil de facturación que se usa para definir las propiedades de la factura, como la facturación a, el número de pedido de compra y los términos de pago. Esta información puede administrarse en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfiles de facturación</a> . Para obtener más información acerca de los perfiles de facturación y cómo puede usarlos para crear opciones de facturación más flexibles para su organización, consulte [Manage Billing profiles](manage-billing-profiles.md). |
| Número de factura |Un número de factura único generado por Microsoft que se usa con fines de seguimiento. |
| Fecha de la factura |Fecha en que se genera la factura, normalmente de cinco a 12 días después del final del ciclo de facturación. Puede comprobar la fecha de la factura en la página de detalles del perfil de facturación. Los gastos que se producen entre el final del período de facturación y la fecha de facturación se incluyen en la factura para el mes siguiente, ya que se encuentran en el siguiente período de facturación. Las fechas de inicio y finalización del período de facturación de cada factura se enumeran en el archivo PDF de la factura sobre el **Resumen de facturación**.|
| Términos de pago |Cómo paga la factura de Microsoft. *30 días* de la red significa que usted paga siguiendo las instrucciones de la factura, en un plazo de 30 días a partir de la fecha de facturación. |

## <a name="understand-the-billing-summary"></a>Descripción del Resumen de facturación

El **Resumen de facturación** muestra el Resumen de los cargos desde el período de facturación anterior, los créditos que se aplicaron, los impuestos y el importe total debido.

| Term | Description |
| --- | --- |
| Cargos|Número total de productos adquiridos para este período de facturación y sus cargos y impuestos relacionados. Las compras se agregan para proporcionar una vista concisa de la factura. |
| Créditos |Créditos que ha recibido de devoluciones |
| Créditos de Azure aplicados |Los créditos de Azure que se aplican automáticamente a Azure cobran cada período de facturación. Si no tiene ningún crédito de Azure, este campo está oculto. Para obtener más información sobre los créditos de Azure, vea [realizar un seguimiento del saldo crediticio de Azure Customer Agreement](https://docs.microsoft.com/en-us/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotal |El importe antes de impuestos debido |
| Impuestos |El tipo y la cantidad de impuestos que se pagan, en función del país del perfil de facturación. Si no tiene que pagar impuestos, no se mostrará ningún impuesto en su factura. |

### <a name="understand-your-charges"></a>Comprender los gastos

Las páginas de cargos muestran el costo desglosado por producto. Para los clientes de Azure, los cargos podrían estar organizados por sección de facturas. Para obtener más información sobre cómo se usan las secciones de facturas con productos de Azure, vea [secciones de facturas](https://docs.microsoft.com/en-us/azure/billing/billing-mca-overview#invoice-sections) en Introducción [a su cuenta de facturación de contratos de clientes de Microsoft](https://docs.microsoft.com/en-us/azure/billing/billing-mca-overview). Dentro de cada pedido de producto, el costo se desglosa por familia de servicios.

| Term |Description |
| --- | --- |
| Precio unitario | Precio unitario efectivo del servicio (en la moneda de precios) que se usa para calcular el cargo. Este precio es único para un producto, una familia de servicios, un medidor y una oferta. |
| Cdad | Cantidad adquirida o consumida durante el período de facturación |
| Cargos/créditos | Importe neto de los cargos después de que se apliquen créditos/reembolsos |
| Crédito de Azure | La cantidad de créditos de Azure aplicados a los cargos/créditos |
| Tasa de impuestos | Tasa de impuestos, según el país |
| Importe de impuestos | Importe de impuestos aplicado a la compra según la tasa de impuestos |
| Total | La cantidad total a pagar para la compra |

Los detalles de los elementos de línea varían en función del tipo de producto por el que se va a cargar. Por ejemplo, para los productos de Azure, se muestra la cantidad de créditos de Azure aplicados. Los productos basados en un asiento muestran un precio unitario y una cantidad. Los detalles de la factura describen los productos comprados, los descuentos o los créditos que se han aplicado, el tipo y el importe del impuesto y los totales del artículo de línea.

`Total = Charges - Azure Credit + Tax`

La cantidad total que debe pagarse para cada familia de servicios se calcula restando créditos de Azure de créditos y cargos, y agregando impuestos:

`Total = Charges/Credits - Azure Credit + Tax`

Si en su factura hay cargas de Azure en las que desea obtener más detalles, consulte Understanding [charges on Your Customer Agreement Invoice](https://docs.microsoft.com/en-us/azure/billing/billing-mca-understand-your-bill).

## <a name="understand-the-last-invoice-page"></a>Comprender la última página de la factura

### <a name="payment-instructions"></a>Instrucciones de pago

En la parte inferior de la factura hay instrucciones sobre cómo pagar la factura. Puede pagar por cable, cheque o en línea.

### <a name="publisher-information"></a>Información del publicador

Si tiene servicios de terceros en su factura, el nombre y la dirección de cada editor aparece en la parte inferior de la factura.

## <a name="view-your-online-invoice"></a>Ver su factura en línea

Las facturas están disponibles en línea. Un vínculo a su factura en línea está disponible en su factura de PDF y desde una notificación por correo electrónico. La factura en línea es expansible para que pueda ver los cargos en su factura y ver más detalles para cada elemento. La factura en línea incluye:

- **Detalles** &mdash; de precios información adicional que incluye detalles sobre descuentos y precios de productos.

- **Pago** &mdash; en línea puede elegir realizar un pago en línea desde la factura.

- **Azure cost Management** &mdash; for Azure los clientes, las facturas en línea incluyen un vínculo a la administración de costos de Azure.

### <a name="to-view-your-online-invoice"></a>Para ver la factura en línea

1. En el centro de administración, vaya a **la** \> página <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">facturas & pagos</a> .

2. Para descargar la versión de. pdf de la factura, elija **Descargar factura PDF** en la fila de la factura que desea ver.

3. Para ver su factura en línea, elija una factura de la lista. También puede descargar el archivo. pdf de la página de detalles de la factura.

## <a name="need-help-contact-support"></a>¿Necesita ayuda? Póngase en contacto con el servicio de soporte técnico.

Si tienes preguntas o necesitas ayuda con los créditos de Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crea una solicitud de soporte técnico con Azure support</a>.

Si tiene alguna pregunta o necesita ayuda con la factura en el centro de administración de Microsoft 365, [póngase en contacto con soporte técnico para productos empresariales](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products).