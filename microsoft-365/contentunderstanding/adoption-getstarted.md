---
title: 'Adopción de Microsoft SharePoint Syntex: Introducción'
description: Aprenda a usar e implementar SharePoint Syntex en su organización para ayudarle a resolver sus problemas empresariales.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7a0bd04121d7400cced22e43a539bd21c45a7fc3
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976584"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Adopción de Microsoft SharePoint Syntex: introducción

Piense que los servicios de contenido inteligente disponibles en SharePoint Syntex tienen tres partes:

- **Descripción del contenido: cree** modelos de IA sin código para clasificar y extraer información del contenido para aplicar automáticamente metadatos para la detección y reutilización de conocimientos. Obtenga más información sobre [la comprensión del contenido.](document-understanding-overview.md)
- **Procesamiento de contenido:** Automatice la captura, la ingesta y la categorización del contenido y optimice los procesos centrados en el contenido mediante Power Automate. Obtenga más información sobre [el procesamiento de contenido.](form-processing-overview.md)
- **Cumplimiento de contenido:** Controlar y administrar el contenido para mejorar la seguridad y el gobierno con la integración con Microsoft Information Protection.

Con las nuevas funcionalidades y servicios de IA, puede crear aplicaciones de descripción y clasificación de contenido directamente en el flujo de administración de contenido con SharePoint Syntex. Hay dos formas diferentes de comprender el contenido. El tipo de modelo que use se basa en el formato de archivo y el caso de uso:

| Procesamiento de formularios | Comprensión de documentos |
|:-------|:-------|
| Creado a partir de la biblioteca de documentos. | Creado en el centro de contenido, parte de SharePoint Syntex. |
| Modelo creado en el generador de IA. | Modelo creado en la interfaz nativa. |
| Se usa para formatos de archivo semiestructurados. | Se usa para formatos de archivo no estructurados. |
| Clasificador configurable. | Clasificador que se puede entrenar con extractores opcionales. |
| Restringido a una sola biblioteca. | Se puede aplicar a varias bibliotecas. |
| Entrena en formato PDF, JPG, PNG, total 50 MB/500 pp. | Entren en 5-10 archivos PDF, Office o correo electrónico, incluidos ejemplos negativos. |

En la siguiente tabla se explica la disponibilidad y las licencias de SharePoint Syntex:

| Procesamiento de formularios | Comprensión de documentos |
|:-------|:-------|
| El procesamiento de formularios se basa en Power Platform. <br>Para obtener información acerca de la disponibilidad global para Power Platform y el Generador de IA, consulte [Disponibilidad de La plataforma de energía.](https://dynamics.microsoft.com/geographic-availability/) | Disponible en todas las regiones. |
| Usa créditos del Generador de IA.<br>Los créditos se pueden comprar en lotes de 1M.<br>Se incluyen créditos de 1M cuando se compran más de 300 licencias de SharePoint Syntex.<br>Los créditos 1M permitirán el procesamiento de 2000 páginas de archivo. | Los modelos funcionan en todos los idiomas del alfabeto latino. Además de inglés: alemán, sueco, francés, español, italiano y portugués. |
| Aprovisionado en el entorno de servicio de datos común predeterminado. | No tiene restricciones de capacidad. |

Para obtener más información acerca de las unidades y créditos del Generador de IA, consulta [licencias del Generador de IA.](https://docs.microsoft.com/ai-builder/administer-licensing)

SharePoint Syntex se integra con las características de cumplimiento de Microsoft 365, como:

- Etiquetas de retención que definen la directiva de registros en función de la antigüedad del documento o eventos externos.
- Etiquetas de confidencialidad que establecen dlp, cifrado, uso compartido y directivas de acceso condicional.

Los usuarios pueden aplicar etiquetas o los pueden aplicar automáticamente los modelos de IA de SharePoint Syntex. Los planes de archivos y análisis proporcionan una administración escalada del uso de etiquetas y las directivas.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificar escenarios empresariales piloto para optimizar

Para prepararse para usar SharePoint Syntex en su organización, primero debe comprender los escenarios en los que será útil. El motivo ayuda a determinar qué modelo se necesita y cómo estructurar la organización en función de dónde se aplicará el modelo. Estos son algunos escenarios en los que la comprensión de documentos puede ayudar a su organización:

- Procesamiento de contenido: procesar contratos, declaraciones de trabajo y otros documentos de tipo formulario. Admisión de los formularios, entrena el modelo para comprender y asignar los campos y, a continuación, ejecuta los formularios para recopilar automáticamente los datos. Para obtener más información, vea [Información general sobre el procesamiento de formularios.](form-processing-overview.md)
- Análisis de facturas: extraiga los detalles relevantes de las facturas y asegúrese de que cumplen con la directiva o se están procesando correctamente.

Piense en las formas en que SharePoint Syntex puede ayudar a su organización:

- Automatizar procesos de negocio
- Mejorar la precisión de búsqueda
- Administrar el riesgo de cumplimiento

### <a name="form-processing-scenario-example"></a>Ejemplo de escenario de procesamiento de formularios

Por ejemplo, puede configurar un proceso con las características de SharePoint Syntex y Power Automate para realizar un seguimiento y supervisar las facturas.

1. Configure una biblioteca para almacenar los documentos de factura.
1. Entrena el modelo para que reconozca los campos de los documentos.
1. Extraiga los campos de los que desea realizar un seguimiento en una lista.
1. Configurar un flujo para notificarle eventos específicos, como:
    - Se agrega una nueva factura.
    - Una factura ha pasado su fecha de vencimiento.
    - Una factura es para un importe que es mayor que el importe de aprobación automática.

![Seguimiento y supervisión de facturas con SharePoint Syntex y Power Automate](../media/content-understanding/process-invoices-flow.png)

Al automatizar este escenario, puede:

- Ahorre tiempo y dinero extrayendo automáticamente datos de las facturas en lugar de hacerlo manualmente.
- Reduzca los posibles errores y garantice un mejor cumplimiento mediante el uso de flujos de trabajo para actuar en las facturas y notificarle cualquier problema.

### <a name="document-understanding-scenario-example"></a>Ejemplo de escenario de descripción de documentos

Como otro ejemplo, puede configurar un proceso para identificar los contratos que su empresa tiene con otras empresas o personas. Puede configurar un modelo para extraer información clave de esos contratos, como el nombre del cliente, las tarifas, las fechas u otra información importante, y agregarlo a la biblioteca como campos que puede ver rápidamente. Además, puede aplicar una etiqueta de retención en la biblioteca de documentos para asegurarse de que los contratos no se puedan eliminar antes de un período de tiempo específico para el cumplimiento adecuado de las normativas empresariales.

1. Empiece en el centro de contenido y cree un nuevo modelo de comprensión de documentos para los contratos.
1. Cargue documentos de ejemplo para obtener ejemplos positivos y negativos y, a continuación, ejecute la formación para identificar los documentos del contrato y revisar los resultados.
1. Entrena al extractor para identificar los campos de los contratos, como el nombre del cliente, la tarifa y la fecha, y luego prueba el extractor.
1. Una vez completado el modelo, aplique el modelo a una biblioteca donde pueda cargar contratos.
1. Aplique una etiqueta de retención al campo de fecha para que los contratos se conserven en la biblioteca durante el tiempo que su organización requiera para los contratos.

![Seguimiento y supervisión de contratos con SharePoint Syntex y etiquetas de retención](../media/content-understanding/process-contracts-flow.png)

Al automatizar este escenario, puede:

- Ahorre tiempo y dinero extrayendo automáticamente datos de los contratos en lugar de hacerlo manualmente.
- Garantizar un mejor cumplimiento mediante el uso de etiquetas de retención para garantizar que los contratos se conserven correctamente.

### <a name="tips-for-identifying-scenarios"></a>Sugerencias para identificar escenarios

Cuando piense en qué escenarios empresariales debe tener en cuenta, haga las siguientes preguntas:

- ¿Resuelve un problema real?
- ¿Se usará ampliamente o tendrá un impacto general?
- ¿Se puede obtener?
- ¿Se puede medir el éxito?

Priorizar escenarios en función del impacto y la facilidad de implementación. Haga que el área de enfoque inicial tenga un mayor impacto en los escenarios que también se pueden implementar fácilmente. Priorizar escenarios de menor impacto que son difíciles de implementar.

## <a name="identify-roles--responsibilities"></a>Identificar roles & responsabilidades

Determinar quién de la organización compilará y administrará los modelos? Pueden estar implicados los siguientes roles:

| Administrador de SharePoint/Knowledge | Administrador de Power Platform | Administrador de conocimientos | Propietario del modelo |
|:-------|:-------|:-------|:-------|
| Rol AAD| Rol AGREGAR | Rol AAD | Expertos: |
| Configurar el procesamiento del formulario | Configuración del entorno de servicio de datos común para el procesamiento de formularios | Recopilar casos de uso | Recopilar casos de uso empresarial |
| Administrar centros de contenido y permisos| Comprar y asignar créditos AIB | Establecer procedimientos recomendados y revisar el análisis del modelo | Crear y aplicar modelos |

El administrador de conocimientos, el propietario del proceso empresarial y el propietario del modelo de contenido crean modelos de ejemplo y la adopción de los campeones en la organización.
Otras personas que pueden estar involucradas: administrador de cumplimiento, administradores de taxonomía.

¿Dónde crearán y aplicarán los modelos? ¿Hay procesos o repositorios existentes que se puedan mejorar?

- Procesamiento de formularios: decida qué sitios recibirán la acción de procesamiento de formularios.
- Document understanding: You can create multiple content centers for different business areas.

## <a name="strategic-positioning"></a>Posicionamiento estratégico

Trabaje con las partes interesadas para asegurarse de que están alineadas en la estrategia de uso de SharePoint Syntex. Investigue y proporcione los siguientes recursos para ayudar con este posicionamiento:

- Resultados empresariales:
  - Posibles resultados fiscales
  - Posibles resultados de agilidad
  - Plantilla de resultados empresariales
- Buy-in/alignment de patrocinadores para participantes/ejecutivos
  - Presentación de casos empresariales
  - Modelos financieros
  - Preparación de la empresa: cultura

## <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Identifique las partes interesadas de su proyecto.

|Función |Responsibilities |Department |
|:-------|:-------|:--------|
| Patrocinadores ejecutivos   | Comunicar valores y visión de alto nivel a la empresa   |  Liderazgo ejecutivo   |
| Clientes potenciales del proyecto | Supervisar todo el proceso de lanzamiento y ejecución de inicio | Administración de proyectos |
| Administradores de conocimientos| Crear y administrar los centros de contenido | TI u otro departamento|
| Administradores de contenido y propietarios de modelos| Recopilar casos de uso y crear y aplicar modelos | Cualquier departamento|
| Expertos: | Ayudar a evangelilizar y administrar el control de las quejas | Cualquier departamento (personal) |
| Administrador de inquilinos | Configuración de las opciones de nivel de inquilino | Departamento de TI|
| Administrador de Power Platform| Configuración del entorno común de servicios de datos | Departamento de TI|

> [!Note]
> Aunque recomendamos que cada uno de estos roles se cumpla a lo largo de la implementación, es posible que no necesite todos ellos para empezar a trabajar con la solución identificada.

## <a name="readiness-checklist"></a>Lista de comprobación de preparación

Para prepararse para implementar SharePoint Syntex, debe:

![Preparación para la comprensión del contenido](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planear el estado final
    - Los modelos de comprensión de documentos son los medios, no el final.
    - Planee aprovechar el valor de los metadatos extraídos con:
      - Búsqueda
      - Filtrado y formato de vista
      - Cumplimiento
      - Automatización
2. Identificación
    - Comprender la arquitectura de la información existente y el uso de características de administración de contenido.
    - ¿Los tipos de contenido existentes son buenos candidatos para los modelos?
    - ¿Qué procesos existentes se mejorarían con los metadatos?
3. Diseño
    - Diseñar el enfoque de la arquitectura de la información, los metadatos administrados y los tipos de contenido
    - Diseñe el proceso de definición, creación y administración.

## <a name="engage-your-organization"></a>Interactuar con la organización

1. Identificar a los poseedores de la participación, confirmar escenarios y desarrollar un plan de proyecto.
1. Configure las opciones y aplique licencias.
1. Empezar a concienciar y formar: contratar campeones.
1. Implementación por fases.  
1. Recopilar comentarios e iterar.
1. A medida que aumenta el uso, planea los créditos del Generador de IA según sea necesario.
