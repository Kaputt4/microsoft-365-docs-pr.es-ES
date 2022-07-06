---
title: Más información sobre las plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Comprenda cómo usar y administrar plantillas para compilar evaluaciones en Microsoft Purview Compliance Manager. Cree y modifique plantillas mediante un archivo de Excel con formato.
ms.openlocfilehash: ac4d3fb6f7a43aa642b9d8b343a68c9f38f29e25
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635653"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>Más información sobre las plantillas de evaluación en el Administrador de cumplimiento

**En este artículo:** Comprenda **cómo funcionan las plantillas** y **cómo administrarlas** desde la página de plantillas de evaluación. Obtenga instrucciones para **crear** nuevas plantillas, **ampliar** y **modificar** plantillas existentes, **dar formato a los datos de plantilla con Excel** y exportar **informes** de plantillas.

> [!IMPORTANT]
> Las plantillas de evaluación que están disponibles para su organización dependen del contrato de licencia. [Revise los detalles](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-compliance-manager).

## <a name="templates-overview"></a>Introducción a las plantillas

Una plantilla es un marco de controles para crear una evaluación en el Administrador de cumplimiento. Nuestro completo conjunto de plantillas puede ayudar a su organización a cumplir con los requisitos nacionales, regionales y específicos del sector que rigen la recopilación y el uso de datos. Nos referimos a las plantillas con el mismo nombre que su certificación o regulación subyacente, como la plantilla RGPD de la UE y la plantilla ISO/IEC 27701:2019.

## <a name="template-versions-microsoft-and-universal"></a>Versiones de plantilla: Microsoft y universal

El administrador de cumplimiento se puede usar para evaluar diferentes tipos de productos. Todas las plantillas, excepto la plantilla predeterminada de [base de referencia de Microsoft Data Protection](compliance-manager-assessments.md#data-protection-baseline-default-assessment) , se incluyen en dos versiones:

1. Una versión que se aplica a un producto predefinido, como Microsoft 365, y
2. Una versión universal que se puede adaptar para adaptarse a otros productos.

Las evaluaciones de plantillas universales son más generalizadas, pero ofrecen una mayor versatilidad, ya que pueden ayudarle a realizar un seguimiento del cumplimiento de su organización fácilmente en varios productos.

Tenga en cuenta que los clientes de la comunidad gubernamental de EE. UU. (GCC) moderados, altos de GCC y del Departamento de Defensa (DoD) no pueden usar actualmente plantillas universales.

## <a name="template-availability-and-licensing"></a>Disponibilidad y licencias de plantillas

Hay dos categorías de plantillas en el Administrador de cumplimiento: incluido y premium.

1. **Las plantillas incluidas** se conceden mediante la licencia del Administrador de cumplimiento y cubren las normativas y requisitos clave. Para obtener más información sobre qué plantillas están disponibles en el contrato de licencia, consulte [detalles de licencias](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager).
2. **Las plantillas Premium** para cubrir necesidades y escenarios adicionales se pueden obtener mediante la compra de licencias de plantilla.

Cuando empiece a crear evaluaciones, el Administrador de cumplimiento realizará un seguimiento de cuántas plantillas están activas para poder supervisar el uso. Para más información, consulte [Plantillas activas e inactivas](compliance-manager-templates.md#active-and-inactive-templates).

Vea la [lista completa de plantillas](compliance-manager-templates-list.md) disponibles en el Administrador de cumplimiento.

### <a name="purchase-premium-template-licenses"></a>Compra de licencias de plantilla Premium

Las licencias de plantilla se pueden obtener mediante uno o varios de estos métodos, según el contrato de licencia de Compliance Manager. Una vez finalizada la compra, las plantillas deben estar disponibles en el inquilino en un plazo de 48 horas.

**Comercial y GCC moderado**

Las cuentas comerciales y de GCC Moderate pueden comprar licencias de plantilla en el centro de administración ([obtenga más información sobre las suscripciones, las licencias y la facturación](/microsoft-365/commerce/)). Seleccione la cantidad de licencias que desea comprar y su plan de pago.

Vínculos de compra:

- [Comercial](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC Moderate](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

También puede adquirir licencias a través de su participación en el [programa Proveedor de soluciones](https://partner.microsoft.com/membership/cloud-solution-provider) en la nube o [licencias por volumen](https://www.microsoft.com/licensing/licensing-programs/licensing-programs).

**Cuentas de GCC High y DOD**

Las cuentas GCC High y DOD deben comprar licencias de plantilla a través de [licencias por volumen](https://www.microsoft.com/licensing/licensing-programs/licensing-programs).

### <a name="try-out-premium-templates"></a>Probar plantillas premium

Para probar las plantillas Premium antes de realizar una compra, también puede adquirir versiones de prueba de las licencias. Las licencias de prueba son válidas para hasta 25 plantillas durante 90 días. Una vez que obtenga la licencia de prueba, las plantillas deben estar disponibles en el inquilino en un plazo de 48 horas.

Si su organización tiene una licencia comercial para el Administrador de cumplimiento, puede aprender a iniciar la evaluación en [Acerca de la evaluación gratuita para las evaluaciones premium de Microsoft Purview Compliance Manager](compliance-easy-trials-compliance-manager-assessments.md).

Si su organización tiene una licencia GCC o DOD, elija el vínculo de prueba adecuado para su organización:

- [GCC Moderate](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC High](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [DOD](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>Plantillas activas e inactivas

Las plantillas mostrarán un estado de activación como activo o inactivo:

- Una plantilla se considera **activa** una vez que se crea una evaluación a partir de esa plantilla.
- Una plantilla se considera **inactiva** si su organización no la usa para una evaluación.

Si vincula las evaluaciones a una plantilla Premium comprada, esa plantilla estará activa durante un año. Tu compra se renovará automáticamente a menos que canceles.

#### <a name="activated-templates-counter"></a>Contador de plantillas activadas

La página de evaluación y la página de plantillas de evaluación tienen un contador **de plantillas activado** cerca de la parte superior. El contador muestra el número de plantillas en uso fuera del número que puede usar según el contrato de licencia. El uso de plantillas se cuenta en el nivel de certificación.

Por ejemplo, si el contador muestra 2/5, esto significa que su organización ha activado 2 plantillas de las 5 que están disponibles para su uso.

Si el contador muestra 5/2, esto indica que su organización supera sus límites y necesita comprar 3 de las plantillas Premium en uso.

Las plantillas para un producto predefinido, como Microsoft 365, tienen licencias conjuntas con las versiones universales de la misma plantilla. Esto le permite usar la misma certificación subyacente en más de un producto. El uso de una o ambas versiones de la misma plantilla solo contará como una plantilla activada.

Para obtener más información, consulte [Guía de licencias del Administrador de cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager).

## <a name="view-and-manage-templates"></a>Visualización y administración de plantillas

La página de plantillas de evaluación del Administrador de cumplimiento muestra una lista de plantillas y detalles clave sobre ellas. La lista incluye plantillas proporcionadas por el Administrador de cumplimiento, así como las plantillas que su organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla basada en la certificación, el ámbito del producto, el país, el sector, quién la creó y si la plantilla está habilitada para la creación de la evaluación.

Seleccione una plantilla de su fila para abrir su página de detalles. Esta página contiene una descripción de la plantilla y más información sobre la certificación, el ámbito y los detalles de los controles. En esta página puede seleccionar los botones adecuados para crear una evaluación, exportar los datos de plantilla a Excel o modificar la plantilla.

## <a name="create-an-assessment-template"></a>Creación de una plantilla de evaluación

Para crear su propia plantilla para evaluaciones personalizadas en el Administrador de cumplimiento, usará una hoja de cálculo de Excel con formato especial para ensamblar los datos de control necesarios. Después de completar la hoja de cálculo, la importará en el Administrador de cumplimiento. Para más información, consulte [Creación de una plantilla de evaluación](compliance-manager-templates-create.md).

## <a name="modify-an-assessment-template"></a>Modificación de una plantilla de evaluación

Al trabajar con evaluaciones en el Administrador de cumplimiento, es posible que desee modificar una plantilla de evaluación que ha creado. El proceso es similar al proceso de creación de plantillas en el que cargará un archivo de Excel con formato con los datos de la plantilla. Para obtener más información sobre cómo realizar cambios y cómo conservar los datos que todavía desea mantener, consulte [Modificación de una plantilla de evaluación](compliance-manager-templates-modify.md).

## <a name="extend-an-assessment-template"></a>Extensión de una plantilla de evaluación

El Administrador de cumplimiento ofrece la opción de agregar sus propios controles y acciones de mejora a una plantilla existente. Este proceso se denomina extensión de una plantilla. Para ampliar una plantilla, usará instrucciones especiales para agregar a los datos de la plantilla, en función de si va a ampliar las plantillas de evaluación de Microsoft o las plantillas de evaluación universal. Para más información, consulte [Extensión de una plantilla de evaluación](compliance-manager-templates-extend.md).

## <a name="format-assessment-template-data-in-excel"></a>Dar formato a los datos de plantilla de evaluación en Excel

Al crear, modificar o ampliar plantillas de evaluación en el Administrador de cumplimiento, trabajará con hojas de cálculo de Excel que usan un formato y un esquema específicos. Estas especificaciones deben seguirse para que los archivos se importen correctamente. Para obtener más información, consulte [Formatear datos de plantilla de evaluación en Excel](compliance-manager-templates-format-excel.md).

## <a name="export-a-template"></a>Exportación de una plantilla

Puede exportar un archivo de Excel que contenga todos los datos de una plantilla. Tendrá que exportar una plantilla para modificarla, ya que este será el archivo de Excel que edite y cargue en el [proceso de modificación](compliance-manager-templates-modify.md). También puede exportar una plantilla como referencia si desea usar datos de ella al crear una nueva plantilla personalizada.

Para exportar la plantilla, vaya a la página de detalles de la plantilla y seleccione el botón **Exportar a Excel** .

Tenga en cuenta que al exportar una plantilla que extendió desde una plantilla del Administrador de cumplimiento, el archivo exportado solo contendrá los atributos que agregó a la plantilla. El archivo exportado no incluirá los datos de plantilla originales proporcionados por Microsoft. Para obtener dicho informe, consulte las instrucciones para [exportar un informe de evaluación](compliance-manager-assessments.md#export-an-assessment-report).
