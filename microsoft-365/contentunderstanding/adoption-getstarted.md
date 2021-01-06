---
title: 'Adopción de Microsoft SharePoint Syntex: introducción'
description: Obtenga información sobre cómo usar e implementar SharePoint Syntex en su organización para ayudarle a resolver los problemas de su empresa.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 95e1ad15a62762c8b28203e178d4d4ae7906e38a
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760247"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Adopción de Microsoft SharePoint Syntex: introducción

Piense en los servicios de contenido inteligente disponibles en SharePoint Syntex como si tuvieran tres partes:

- **Descripción del contenido:** cree modelos AI sin código para clasificar y extraer información de contenido para aplicar automáticamente metadatos para la detección y reutilización de conocimientos. Obtenga más información sobre el [conocimiento del contenido](document-understanding-overview.md).
- **Procesamiento de contenido:** Automatizar la captura, la recopilación y la categorización del contenido y simplificar los procesos centrados en el contenido mediante el uso de energía automatizada. Obtenga más información sobre el [procesamiento de contenido](form-processing-overview.md).
- **Cumplimiento del contenido:** Controle y administre contenido para mejorar la seguridad y el gobierno con integración con la protección de la información de Microsoft.

Con los nuevos servicios y capacidades de AI, puede crear aplicaciones de clasificación y comprensión de contenido directamente en el flujo de administración de contenido con SharePoint Syntex:

|Entrada manual| Procesamiento de formularios | Descripción de los documentos |
|:-------|:--------|:--------|
| Entrada de datos y mucho trabajo en cualquier contenido. | Identificar los archivos y extraer datos de documentos estructurados o semiestructurados, como formularios o facturas. |  Identificar y extraer datos de documentos no estructurados, como cartas o contratos, donde las entidades de texto que desea extraer residen en oraciones o regiones específicas del documento. |
| Curso.   |  Personalizado y asistido.  | Predefinido y automatizado. |
| Personas que realizan el trabajo. | Impartidos por sus expertos en la materia (SME). | Las PYME están menos involucradas. |

En la siguiente tabla se explica la disponibilidad y las licencias de SharePoint Syntex:

| Procesamiento de formularios | Descripción de los documentos |
|:-------|:-------|
| El procesamiento de formularios se basa en la plataforma de energía. <br>Para obtener información acerca de la disponibilidad global para la plataforma de alimentación y el generador de AI, consulte [Power Platform Availability](https://dynamics.microsoft.com/geographic-availability/). | Disponible en todas las regiones. |
| Usa créditos del generador de AI.<br>Los créditos se pueden comprar en lotes de 1M.<br>los créditos de 1M se incluyen cuando se compran más de 300 licencias de Syntex de SharePoint.<br>los créditos de 1M permitirán el procesamiento de páginas de archivos de 2000. | Los modelos funcionan en todos los idiomas del alfabeto latino. Además del inglés: Alemán, sueco, Francés, español, Italiano y portugués. |
| Aprovisionado en el entorno de servicio de datos común predeterminado. | No tiene restricciones de capacidad. |

Para obtener más información acerca de los créditos del generador de AI y las unidades, consulte [AI Builder Licensing](https://docs.microsoft.com/ai-builder/administer-licensing).

Hay dos formas diferentes de comprender el contenido. El tipo de modelo que usa se basa en el formato de archivo y el caso de uso:

| Procesamiento de formularios | Descripción de los documentos |
|:-------|:-------|
| Creado a partir de una biblioteca de documentos. | Creado en el centro de contenido, parte de SharePoint Syntex. |
| Modelo creado en el generador de AI. | Modelo creado en la interfaz nativa. |
| Se usa para formatos de archivo semiestructurados. | Se usa para los formatos de archivo no estructurados. |
| Clasificador configurable. | Clasificador capacitado con extractores opcionales. |
| Restringido a una única biblioteca. | Puede aplicarse a varias bibliotecas. |
| Entrenar en formato PDF, JPG, PNG, total de 50 MB/500 págs. | Entrenar en 5-10 archivos de correo electrónico, Office o PDF, incluidos ejemplos negativos. |

SharePoint Syntex se integra con las características de cumplimiento de Microsoft 365 como:

- Etiquetas de retención que definen la Directiva de registros basada en la antigüedad del documento o los eventos externos.
- Etiquetas de sensibilidad que configuran las directivas de DLP, cifrado, uso compartido y acceso condicional.

Los usuarios pueden aplicar etiquetas o los modelos AI de SharePoint Syntex pueden aplicarlas automáticamente. Los planes de análisis y archivos proporcionan una administración escalada del uso de etiquetas y de las directivas.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificar escenarios empresariales piloto para optimizar

Para preparar el uso de SharePoint Syntex en su organización, primero necesita comprender los escenarios en los que será útil. El por qué ayuda a determinar qué modelo será necesario y cómo estructurar la organización en función del lugar en el que se aplicará el modelo. Estos son algunos escenarios en los que la comprensión de documentos puede ayudar a su organización:

- Procesamiento de contenido: contratos de proceso, instrucciones de trabajo y otros documentos similares a formularios. Dar la entrada a los formularios, entrenar el modelo para comprender y asignar los campos y, a continuación, ejecutar los formularios a través de para recopilar los datos de forma automática. Para obtener más información, consulte [Form Processing Overview](form-processing-overview.md).
- Análisis de factura: Extraiga los detalles relevantes de sus facturas y asegúrese de que se ajustan a la Directiva o se están procesando correctamente.

Piense en las formas en que SharePoint Syntex puede ayudar a su organización:

- Automatizar procesos empresariales
- Mejorar la precisión de la búsqueda
- Administración de riesgos de cumplimiento

### <a name="form-processing-scenario-example"></a>Ejemplo de escenario de procesamiento de formularios

Por ejemplo, puede configurar un proceso con SharePoint Syntex y automatizar las características para controlar y supervisar las facturas.

1. Configurar una biblioteca para almacenar los documentos de factura.
1. Entrenar el modelo para que reconozca los campos de los documentos.
1. Extraiga los campos de los que desee realizar un seguimiento en una lista.
1. Configure un flujo para notificar eventos específicos, como:
    - Se agrega una nueva factura.
    - Una factura supera su fecha de vencimiento.
    - Una factura es para una cantidad que es mayor que la cantidad de aprobación automática.

![Seguimiento y supervisión de facturas con SharePoint Syntex y automatización de la energía](../media/content-understanding/process-invoices-flow.png)

Al automatizar este escenario, puede:

- Ahorre tiempo y dinero mediante la extracción automática de datos de las facturas en lugar de hacerlo manualmente.
- Reducir los posibles errores y garantizar un mejor cumplimiento mediante el uso de flujos de trabajo para actuar en las facturas y notificar cualquier problema.

### <a name="document-understanding-scenario-example"></a>Ejemplo de escenario de comprensión de documento

Como otro ejemplo, puede configurar un proceso para identificar contratos que su compañía tiene con otras empresas o individuos. Puede configurar un modelo para extraer información clave de estos contratos, como el nombre del cliente, las tarifas, las fechas u otra información importante, y agregarlo a la biblioteca como campos que puede ver rápidamente. Además, puede aplicar una etiqueta de retención en la biblioteca de documentos para asegurarse de que los contratos no se pueden eliminar antes de un período de tiempo específico para cumplir con las regulaciones de la empresa.

1. Empiece en el centro de contenido y cree un documento nuevo que comprenda el modelo de contratos.
1. Cargue documentos de ejemplo para ver ejemplos positivos y negativos y, a continuación, ejecute el curso para identificar los documentos del contrato y revise los resultados.
1. Entrenar al extractor para identificar los campos de los contratos, como el nombre del cliente, la tarifa y la fecha y, a continuación, probar el extractor.
1. Una vez finalizado el modelo, aplique el modelo a una biblioteca en la que pueda cargar contratos.
1. Aplique una etiqueta de retención al campo de fecha, de modo que los contratos se retengan en la biblioteca durante el período de tiempo que la organización requiera para los contratos.

![Seguimiento y supervisión de contratos con SharePoint Syntex y etiquetas de retención](../media/content-understanding/process-contracts-flow.png)

Al automatizar este escenario, puede:

- Ahorre tiempo y dinero mediante la extracción automática de datos de los contratos en lugar de hacerlo manualmente.
- Garantizar un mejor cumplimiento mediante el uso de etiquetas de retención para asegurarse de que los contratos se retienen correctamente.

### <a name="tips-for-identifying-scenarios"></a>Sugerencias para identificar escenarios

Al pensar sobre qué escenarios empresariales debe plantearse, hágase las siguientes preguntas:

- ¿Se solucionó un problema real?
- ¿Se usará mucho o tiene un gran impacto?
- ¿Se obtiene?
- ¿Puede medir el éxito?

Priorizar los escenarios según el impacto y la facilidad de implementación. Haga que su área de enfoque inicial tenga escenarios de impacto superior que también se pueden implementar fácilmente. Anular la prioridad de escenarios de impacto más bajos que son difíciles de implementar.

## <a name="identify-roles--responsibilities"></a>Identificación de funciones & responsabilidades

¿Qué usuarios de la organización crearán y administrarán los modelos? Los siguientes roles podrían estar implicados:

| SharePoint/administrador de conocimiento | Administrador de plataforma de energía | Administrador de conocimiento | Propietario del modelo |
|:-------|:-------|:-------|:-------|
| Rol de AAD| Agregar rol | Rol de AAD | Expertos: |
| Configurar el procesamiento del formulario | Configuración del entorno de servicio de datos comunes para el procesamiento de formularios | Recopilar casos de uso | Recopilar casos de uso de negocio |
| Administración de centros de contenido y permisos| Comprar y asignar créditos AIB | Establecimiento de procedimientos recomendados y revisión del análisis de modelos | Creación y aplicación de modelos |

El administrador de conocimiento, el propietario del proceso empresarial y el propietario del modelo de contenido crean modelos de ejemplo y la adopción de campeóns en la organización.
Otros usuarios que pueden participar: administrador de cumplimiento, administradores de taxonomía.

¿Dónde compilarán y aplicarán los modelos? ¿Hay procesos o repositorios existentes que se puedan mejorar?

- Procesamiento de formularios: decida qué sitios recibirán la acción de procesamiento de formulario.
- Descripción del documento: puede crear varios centros de contenido para diferentes áreas empresariales.

## <a name="strategic-positioning"></a>Posicionamiento estratégico

Trabaje con las partes interesadas para asegurarse de que están alineadas con la estrategia para usar SharePoint Syntex. Investigue y proporcione los siguientes recursos para ayudarle con esta posición:

- Resultados empresariales:
  - Posibles resultados fiscales
  - Resultados potenciales de la agilidad
  - Plantilla de resultado empresarial
- Partes interesadas/Patrocinador Ejecutivo: compra y alineamiento
  - Barajas de casos empresariales
  - Modelos financieros
  - Preparación de la empresa: referencia cultural

## <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Identifique a las partes interesadas del proyecto.

|Role |Responsibilities |Department |
|:-------|:-------|:--------|
| Patrocinadores ejecutivos   | Comunicar la visión y los valores de alto nivel a la empresa   |  Liderazgo ejecutivo   |
| Jefes de proyecto | Supervisar todo el proceso de ejecución e implementación de inicio | Administración de proyectos |
| Administradores de conocimiento| Creación y administración de centros de contenido | TI u otro departamento|
| Administradores de contenido y propietarios de modelos| Recopilar casos de uso y crear y aplicar modelos | Cualquier departamento|
| Expertos: | Ayudar a repartir y administrar el manejo de objeciones | Cualquier departamento (personal) |
| Administrador de inquilinos | Configurar la configuración de nivel de inquilino | Departamento de ti|
| Administrador de plataforma de energía| Configuración del entorno de servicios de datos comunes | Departamento de ti|

> [!Note]
> Aunque le recomendamos que cada una de estas funciones se cumplan a lo largo de su distribución, es posible que no se requiera todo para empezar a trabajar con la solución identificada.

## <a name="readiness-checklist"></a>Lista de comprobación de preparación

Para prepararse para implementar SharePoint Syntex, debe:

![Preparación para la comprensión del contenido](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planeación del estado final
    - Document: los modelos comprenden los medios, no el final.
    - Planee el aprovechamiento del valor de los metadatos extraídos con:
      - Búsqueda
      - Filtrar y ver el formato
      - Cumplimiento
      - Automatización
2. Identificación
    - Comprenda la arquitectura de la información existente y el uso de la característica de administración de contenido.
    - ¿Los tipos de contenido existentes son buenos candidatos para los modelos?
    - ¿Qué procesos existentes mejorarían mediante metadatos?
3. Diseño
    - Diseñar el enfoque de la arquitectura de la información, los metadatos administrados y los tipos de contenido
    - Diseñar el proceso de definición, creación y administración.

## <a name="engage-your-organization"></a>Hacer participar a su organización

1. Identificar a los titulares de apuestas, confirmar los escenarios y desarrollar el plan del proyecto.
1. Configure las opciones y aplique licencias.
1. Comenzar el reconocimiento y la formación: Campeones de la contratación.
1. Implementar en fases.  
1. Recopilar comentarios y realizar iteraciones.
1. A medida que el uso aumenta el plan de los créditos del generador de AI según sea necesario.
