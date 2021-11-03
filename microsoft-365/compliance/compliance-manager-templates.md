---
title: Trabajar con plantillas de evaluación en Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
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
description: Comprenda cómo usar y administrar plantillas para crear evaluaciones en El Administrador de cumplimiento de Microsoft. Cree y modifique plantillas con un archivo Excel formato.
ms.openlocfilehash: 99e243e86c66babd9a983ae6df891f4094cdbb83
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701616"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>Obtenga información sobre las plantillas de evaluación en el Administrador de cumplimiento

**En este artículo:** Comprenda **cómo funcionan las plantillas** y cómo **administrarlas desde** la página de plantillas de evaluación. Obtenga instrucciones para **crear nuevas**  plantillas, **ampliar** y modificar plantillas existentes, dar formato a los datos de la plantilla **con** Excel y exportar informes de **plantilla**.

> [!IMPORTANT]
> Las plantillas de evaluación que están disponibles para su organización dependen del contrato de licencia. [Revise los detalles](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="templates-overview"></a>Introducción a plantillas

Una plantilla es un marco de controles para crear una evaluación en el Administrador de cumplimiento. Nuestro conjunto completo de plantillas puede ayudar a su organización a cumplir con los requisitos nacionales, regionales y específicos del sector que rigen la recopilación y el uso de datos.

Nos referimos a plantillas con el mismo nombre que su certificación o reglamento subyacentes, como la plantilla RGPD de la UE y la plantilla ISO/IEC 27701:2019. Dado que el pesebre de cumplimiento se puede usar para evaluar diferentes tipos de productos, cada plantilla viene en dos versiones: una que se aplica a un producto predefinido, como Microsoft 365, y una versión universal que puede adaptarse a su producto elegido.

Tenga en cuenta que Community (GCC) los clientes moderados, GCC altos y del Departamento de Defensa (DoD) actualmente no pueden usar plantillas universales.

## <a name="template-availability-and-licensing"></a>Disponibilidad y licencias de plantillas

Hay dos categorías de plantillas en el Administrador de cumplimiento: incluidas y premium.

1. **Las plantillas incluidas** se conceden mediante la licencia del Administrador de cumplimiento y cubren las normativas y requisitos clave. Para obtener más información sobre qué plantillas están disponibles en el contrato de licencia, consulte [licensing details](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager).
2. **Premium plantillas para** cubrir necesidades y escenarios adicionales se pueden obtener mediante la compra de licencias de plantilla.

Al empezar a crear evaluaciones, el Administrador de cumplimiento realizará un seguimiento de cuántas plantillas están activas para que pueda supervisar su uso. Para obtener más información, vea [Plantillas activas e inactivas.](compliance-manager-templates.md#active-and-inactive-templates)

Vea la [lista completa de plantillas disponibles](compliance-manager-templates-list.md) en el Administrador de cumplimiento.

### <a name="purchase-premium-template-licenses"></a>Comprar licencias de plantilla premium

Las licencias de plantilla se pueden obtener mediante uno o varios de estos métodos, según el contrato de licencia del Administrador de cumplimiento. Una vez que se haya finalizado la compra, las plantillas deben estar disponibles en el espacio empresarial en un plazo de 48 horas.

**Comercial y GCC moderado**

Las cuentas GCC comerciales y moderadas pueden comprar licencias de plantilla en el Centro de administración (obtenga más información sobre suscripciones, licencias[y facturación).](/microsoft-365/commerce/) Seleccione la cantidad de licencias que desea comprar y su plan de pago.

Vínculos de compra:

- [Comercial](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC Moderado](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

También puede adquirir licencias a través de su participación en el programa [Proveedor de soluciones en la nube o](https://partner.microsoft.com/membership/cloud-solution-provider) licencias [por volumen](https://www.microsoft.com/licensing/licensing-programs/licensing-programs).

**GCC Cuentas altas y de DOD**

GCC Las cuentas high y DOD deben comprar licencias de plantilla a través [de licencias por volumen.](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)

### <a name="try-out-premium-templates"></a>Probar plantillas premium

Para probar las plantillas premium antes de realizar una compra, también puede adquirir versiones de prueba de las licencias. Las licencias de prueba son válidas para un máximo de 25 plantillas durante 90 días. Una vez que obtenga la licencia de prueba, las plantillas deben estar disponibles en el espacio empresarial en un plazo de 48 horas.

Si su organización tiene una licencia comercial para el Administrador de cumplimiento, puede obtener información sobre cómo iniciar la prueba en About [the free trial for Microsoft Compliance Manager premium assessments](compliance-easy-trials-compliance-manager-assessments.md).

Si su organización está bajo una licencia GCC o DOD, elija el vínculo de prueba adecuado para su organización:

- [GCC Moderado](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC High](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [DOD](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>Plantillas activas e inactivas

Las plantillas mostrarán un estado de activación como activo o inactivo:

- Una plantilla se considera **activa** una vez que se crea una evaluación a partir de esa plantilla.
- Una plantilla se considera **inactiva** si su organización no la usa para una evaluación.

Si vinculas cualquier evaluación a una plantilla premium comprada, esa plantilla estará activa durante un año. La compra se renovará automáticamente a menos que canceles.

#### <a name="activated-templates-counter"></a>Contador de plantillas activadas

La página de evaluación y la página de plantillas de evaluación tienen **un contador de plantillas activadas** cerca de la parte superior. El contador muestra el número de plantillas en uso fuera del número que puede usar de acuerdo con el contrato de licencia. El uso de plantillas se cuenta en el nivel de certificación.

Por ejemplo, si el contador muestra 2/5, esto significa que su organización ha activado 2 plantillas de las 5 que están disponibles para usar.

Si el contador muestra 5/2, esto indica que su organización supera sus límites y necesita comprar 3 de las plantillas premium en uso.

Las plantillas de un producto predefinido, como Microsoft 365, tienen licencias conjuntas con las versiones universales de la misma plantilla. Esto le permite usar la misma certificación subyacente en más de un producto. El uso de una o ambas versiones de la misma plantilla solo contará como una plantilla activada.

Para obtener más información, consulte [Compliance Manager licensing guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager).

## <a name="view-and-manage-templates"></a>Ver y administrar plantillas

La página plantillas de evaluación del Administrador de cumplimiento muestra una lista de plantillas y detalles clave sobre ellas. La lista incluye plantillas proporcionadas por el Administrador de cumplimiento, así como cualquier plantilla que la organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla basada en la certificación, el ámbito del producto, el país, la industria, quién la creó y si la plantilla está habilitada para la creación de evaluaciones.

Seleccione una plantilla de su fila para mostrar su página de detalles. Esta página contiene una descripción de la plantilla y más información sobre los detalles de certificación, ámbito y controles. En esta página puede seleccionar los botones adecuados para crear una evaluación, exportar los datos de plantilla a Excel o modificar la plantilla.

## <a name="create-an-assessment-template"></a>Crear una plantilla de evaluación

Para crear su propia plantilla nueva para evaluaciones personalizadas en el Administrador de cumplimiento, usará una hoja de cálculo Excel formato especial para ensamblar los datos de control necesarios. Después de completar la hoja de cálculo, la importará al Administrador de cumplimiento. Para obtener más información, vea [Create an assessment template](compliance-manager-templates-create.md).

## <a name="modify-an-assessment-template"></a>Modificar una plantilla de evaluación

Al trabajar con evaluaciones en el Administrador de cumplimiento, es posible que desee modificar una plantilla de evaluación que haya creado. El proceso es similar al proceso de creación de plantillas en el que se cargará un archivo Excel con los datos de la plantilla. Para obtener más información sobre cómo realizar cambios y cómo conservar los datos que aún desea mantener, vea [Modify an assessment template](compliance-manager-templates-modify.md).

## <a name="extend-an-assessment-template"></a>Ampliar una plantilla de evaluación

El Administrador de cumplimiento ofrece la opción de agregar sus propios controles y acciones de mejora a una plantilla existente. Este proceso se denomina extensión de una plantilla. Para ampliar una plantilla, usará instrucciones especiales para agregar datos de plantilla, en función de si está ampliando plantillas de evaluación de Microsoft o plantillas de evaluación universal. Para obtener más información, vea [Extend an assessment template](compliance-manager-templates-extend.md).

## <a name="format-assessment-template-data-in-excel"></a>Dar formato a los datos de plantilla de evaluación Excel

Al crear, modificar o ampliar plantillas de evaluación en el Administrador de cumplimiento, trabajará con Excel hojas de cálculo que usan un esquema y un formato específicos. Estas especificaciones deben seguirse para que los archivos se importen correctamente. Para obtener más información, vea [Format assessment template data in Excel](compliance-manager-templates-format-excel.md).

## <a name="export-a-template"></a>Exportar una plantilla

Puede exportar un archivo Excel que contenga todos los datos de una plantilla. Tendrás que exportar una plantilla para modificarla, ya que este será el archivo Excel editar y cargar en el proceso [de modificación.](compliance-manager-templates-modify.md) También puede exportar una plantilla como referencia si desea usar datos a partir de ella al crear una nueva plantilla personalizada.

Para exportar la plantilla, vaya a la página de detalles de la plantilla y seleccione el botón Exportar **a Excel** plantilla.

Tenga en cuenta que al exportar una plantilla que extendió desde una plantilla del Administrador de cumplimiento, el archivo exportado solo contendrá los atributos que agregó a la plantilla. El archivo exportado no incluirá los datos de plantilla originales proporcionados por Microsoft. Para obtener dicho informe, vea las instrucciones para [exportar un informe de evaluación](compliance-manager-assessments.md#export-an-assessment-report).