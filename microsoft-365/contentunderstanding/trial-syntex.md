---
title: Ejecutar una prueba de Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Obtenga información sobre cómo planear y ejecutar un programa piloto de prueba para SharePoint Syntex en su organización.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327149"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Ejecutar una prueba de Microsoft SharePoint Syntex

En este artículo se describe cómo configurar y ejecutar un programa piloto de prueba para implementar SharePoint Syntex en la organización. También recomienda procedimientos recomendados para la prueba.

## <a name="sign-up-for-a-trial"></a>Registrarse para una versión de prueba

La versión de SharePoint Syntex ofrece acceso a 300 usuarios durante 30 días.

> [!NOTE]
> Hasta 300 usuarios se incluyen en la versión de prueba para garantizar la adición automática de 1 millón de créditos de AI Builder. No es necesario incluir 300 usuarios para que una prueba se realice correctamente.

Puede obtener la versión de prueba de uno de los siguientes orígenes:

- Página [SharePoint Syntex producto](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- El [Centro de administración de Microsoft 365](https://admin.microsoft.com)
    1.  Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com).
    2.  Vaya a **Servicios de compra** de  >  **facturación**.
    3.  Desplácese hacia abajo hasta la sección **Complementos**.
    4.  En el icono SharePoint Syntex, seleccione **Detalles**.
    5.  Seleccione **Obtener prueba gratuita**.
    6.  Para confirmar la prueba, siga los pasos del asistente restantes.

Debe ser un administrador Microsoft 365 global o administrador de facturación para activar una versión de prueba.

### <a name="who-should-be-involved-in-a-trial"></a>Quién debe participar en una prueba

|Rol  |Actividad  |
|---------|---------|
|Microsoft 365 administrador global o de facturación    |     Activar la versión de prueba y asignar licencias    |
|Microsoft 365 administrador global o administrador SharePoint administrador     |   Configurar SharePoint Syntex y crear centros de contenido      |
|Usuarios empresariales     |    Creación y pruebas de modelos     |

### <a name="before-you-activate-a-trial"></a>Antes de activar una versión de prueba

Para planear correctamente una SharePoint Syntex prueba, tenga en cuenta los siguientes factores:

- Las pruebas más significativas se completan en escenarios y datos del "mundo real".
- Solo puede activar una versión de SharePoint Syntex una vez por inquilino.

Un inquilino de prueba o demostración puede usarse como una "ejecución en seco" para recorrer los pasos de activación y los controles administrativos. Pero probablemente sea mejor evaluar la creación de modelos en un inquilino de producción.

Para maximizar el valor de una prueba en un inquilino de producción, la planeación y la participación empresarial son esenciales. Debe participar en una o más áreas de negocio para identificar de tres a seis casos de uso que podrían ser posiblemente abordados por SharePoint Syntex. Estos casos de uso deben:

- Incluya escenarios que podrían resolverse mediante el modelo de procesamiento de formularios o de comprensión de documentos.
- Tener una comprensión clara del propósito de los metadatos extraídos; por ejemplo, ver el formato o la automatización mediante Power Automate. Aunque SharePoint Syntex está centrado en clasificar documentos y extraer metadatos, el valor que se va a cuantificar es lo que habilitan estos metadatos.
- Se basa en un conjunto definido de datos; por ejemplo, sitios SharePoint o bibliotecas específicas. Una idea errónea común de SharePoint Syntex es que los modelos de propósito general se pueden aplicar en todo el contenido de la organización. Una vista más precisa es que los modelos se han creado para ayudar a resolver problemas empresariales específicos en ubicaciones dirigidas.

Es posible que todos estos casos de uso no sean adecuados para SharePoint Syntex. El objetivo de una prueba de calidad no es probar que SharePoint Syntex se ajuste a todos los escenarios. En su lugar, la prueba debe ayudarle a comprender mejor el valor del producto.

Para cada uno de los casos de uso planeados, identifique a los usuarios que son expertos en la materia en el proceso o contenido relacionados. La creación de SharePoint Syntex se centra en expertos de dominio en el contenido, en lugar de en profesionales de TI o recursos para desarrolladores.

## <a name="activate-a-trial"></a>Activar una versión de prueba

Al iniciar una prueba, debe:

- Asignar licencias a los usuarios relevantes.
- Realice [una configuración adicional de SharePoint Syntex](set-up-content-understanding.md).
    - Es posible que desee crear [centros de contenido adicionales](create-a-content-center.md).

Después de activar la prueba, puede crear modelos y procesar archivos. Vea [las instrucciones para la creación de modelos](create-a-content-center.md).

## <a name="during-a-trial"></a>Durante una prueba

Los períodos de prueba son limitados, por lo que es mejor centrarse inicialmente en si los SharePoint Syntex pueden clasificar documentos y extraer metadatos para los casos de uso definidos. Una vez terminado el período de prueba, puede evaluar cómo se pueden aprovechar los metadatos.

## <a name="after-a-trial"></a>Después de una prueba

En función del resultado de la prueba, puede decidir si procede al uso de producción de SharePoint Syntex.

### <a name="proceed-to-production-use"></a>Continuar con el uso de producción

Para garantizar la continuidad del servicio, debe comprar el número necesario de licencias y asignar esas licencias a los usuarios. Los usuarios de prueba que no tienen una licencia completa al final del período de prueba no podrán usar completamente SharePoint Syntex.

Es posible que tenga que calcular el uso previsto del procesamiento de formularios y planear la cantidad esperada de créditos de AI Builder. Para obtener ayuda, [vea Estimate the AI Builder capacity that's right for you](https://powerapps.microsoft.com/ai-builder-calculator/).

### <a name="dont-proceed-to-production-use"></a>No continuar con el uso de producción

Si no compra licencias después de la versión de prueba:

- No podrá crear nuevos modelos.
- Las bibliotecas que estaban ejecutando modelos ya no clasificarán automáticamente archivos ni extraerán modelos.
- Los archivos clasificados previamente o los metadatos extraídos no se verán afectados. 
- Los centros de contenido y los modelos de comprensión de documentos no se eliminarán automáticamente. Estos permanecerán disponibles para su uso si decide comprar licencias en el futuro.
- Los modelos de procesamiento de formularios se almacenarán en la instancia de Common Data Services (CDS) del entorno predeterminado de Power Platform. Se podrían usar con licencias futuras para SharePoint Syntex o con funcionalidades de AI Builder en power platform.

## <a name="see-also"></a>Vea también

[Adopción SharePoint Syntex Microsoft: Introducción](adoption-getstarted.md)
