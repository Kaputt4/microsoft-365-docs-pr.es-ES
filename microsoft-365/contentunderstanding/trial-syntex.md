---
title: Ejecución de una prueba de Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom:
- Adopt
- admindeeplinkMAC
search.appverid: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo planear, registrarse y ejecutar un programa piloto de prueba para Microsoft Syntex en su organización.
ms.openlocfilehash: 27770aa818c25b5c18c07a3f8f67a2185964ad37
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564068"
---
# <a name="run-a-trial-of-microsoft-syntex"></a>Ejecución de una prueba de Microsoft Syntex

En este artículo se describe cómo configurar y ejecutar un programa piloto de prueba para implementar Microsoft Syntex en su organización. También recomienda procedimientos recomendados para la prueba.

## <a name="sign-up-for-a-trial"></a>Registrarse para obtener una prueba

La versión de prueba de Syntex da acceso a 300 usuarios durante 30 días.

> [!NOTE]
> Hasta 300 usuarios se incluyen en la prueba para garantizar la adición automática de un millón de créditos de AI Builder. No es necesario incluir 300 usuarios para que una prueba se realice correctamente.

Puede obtener la versión de prueba de uno de los siguientes orígenes:

- Página del [producto Syntex](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- El [Centro de administración de Microsoft 365](https://admin.microsoft.com)
    1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com).
    2. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Servicios**</a> de **compra de facturación** > .
    3. Desplácese hacia abajo hasta la sección **Complementos**.
    4. En el icono de Syntex, seleccione **Detalles**.
    5. Seleccione **Iniciar evaluación gratuita**.
    6. Para confirmar la prueba, siga los pasos restantes del asistente.

Debe ser administrador global de Microsoft 365 o administrador de facturación para activar una prueba.

### <a name="who-should-be-involved-in-a-trial"></a>Quién debe participar en una prueba

|Rol|Actividad|
|---|---|
|Administrador global o administrador de facturación de Microsoft 365|Activación de la prueba y asignación de licencias|
|Administrador global de Microsoft 365 o administrador de SharePoint|Configuración de Syntex y creación de centros de contenido|
|Usuarios empresariales|Compilación y pruebas de modelos|

### <a name="before-you-activate-a-trial"></a>Antes de activar una prueba

Para planear correctamente una evaluación de Syntex, tenga en cuenta los siguientes factores:

- Las pruebas más significativas se completan en escenarios y datos "del mundo real".
- Solo puede activar una prueba de Syntex una vez por inquilino.

Un inquilino de prueba o demostración se puede usar como "ejecución en seco" para recorrer los pasos de activación y los controles administrativos. Pero probablemente sea mejor evaluar la compilación de modelos en un inquilino de producción.

Para maximizar el valor de una prueba en un inquilino de producción, es esencial planear y la participación empresarial. Debe interactuar con una o varias áreas de negocio para identificar entre tres y seis casos de uso que podrían ser abordados por Syntex. Estos casos de uso deben:

- Incluya escenarios que se puedan resolver mediante el modelo de procesamiento de formularios o de comprensión de documentos.
- Comprender claramente el propósito de los metadatos extraídos; por ejemplo, ver el formato o la automatización mediante Power Automate. Aunque Syntex se centra en clasificar documentos y extraer metadatos, el valor que se va a cuantificar es lo que permite estos metadatos.
- Se basa en un conjunto definido de datos; por ejemplo, sitios o bibliotecas específicos de SharePoint. Un concepto erróneo común de Syntex es que los modelos de uso general se pueden aplicar en todo el contenido de la organización. Una vista más precisa es que los modelos se crean para ayudar a resolver problemas empresariales específicos en ubicaciones dirigidas.

Es posible que todos estos casos de uso no sean una buena opción para Syntex. El objetivo de una prueba de calidad no es demostrar que Syntex se ajuste a todos los escenarios. En su lugar, la prueba debería ayudarle a comprender mejor el valor del producto.

Para cada uno de los casos de uso planeados, identifique a los usuarios que son expertos en la materia en el contenido o proceso relacionado. La creación de modelos de Syntex se centra en expertos en dominio en el contenido, en lugar de en profesionales de TI o recursos para desarrolladores.

## <a name="activate-a-trial"></a>Activación de una prueba

Al iniciar una prueba, debe hacer lo siguiente:

- Asigne licencias a los usuarios pertinentes.
- Realice [una configuración adicional de Syntex](set-up-content-understanding.md).
  - Es posible que quiera [crear más centros de contenido](create-a-content-center.md).

Una vez activada la prueba, puede crear modelos y procesar archivos. Consulte [las instrucciones para la creación de modelos](create-a-content-center.md).

## <a name="during-a-trial"></a>Durante una prueba

Los períodos de prueba son limitados, por lo que es mejor centrarse inicialmente en si los modelos de Syntex pueden clasificar documentos y extraer metadatos para los casos de uso definidos. Una vez finalizado el período de prueba, puede evaluar cómo se pueden usar los metadatos.

## <a name="after-a-trial"></a>Después de una prueba

En función del resultado de la prueba, puede decidir si desea continuar con el uso en producción de Syntex.

### <a name="proceed-to-production-use"></a>Continuar con el uso de producción

Para garantizar la continuidad del servicio, debe comprar el número necesario de [licencias](syntex-licensing.md) y asignar esas licencias a los usuarios. Los usuarios de prueba que no tengan una licencia completa al final del período de prueba no podrán usar Syntex por completo.

Es posible que tenga que calcular el uso proyectado del procesamiento de formularios y planear el número esperado de créditos de AI Builder. Para obtener ayuda, consulte [Estimación de la capacidad de AI Builder adecuada para usted](https://powerapps.microsoft.com/ai-builder-calculator/).

### <a name="dont-proceed-to-production-use"></a>No continuar con el uso de producción

Si no compra licencias después de la prueba:

- No podrá crear nuevos modelos.
- Las bibliotecas que estaban ejecutando modelos ya no clasificarán automáticamente los archivos ni extraerán modelos.
- Los archivos previamente clasificados o los metadatos extraídos no se verán afectados.
- Los centros de contenido y los modelos de comprensión de documentos no se eliminarán automáticamente. Estos permanecerán disponibles para su uso si decide comprar licencias en el futuro.
- Los modelos de procesamiento de formularios se almacenarán en la instancia de Dataverse (anteriormente denominada Common Data Service (CDS)) del entorno predeterminado de Power Platform. Se pueden usar con futuras licencias para Syntex o con funcionalidades de AI Builder en Power Platform.

## <a name="see-also"></a>Vea también

[Introducción a la adopción de Microsoft Syntex](adoption-getstarted.md)

[Escenarios y casos de uso para Microsoft Syntex](adoption-scenarios.md)