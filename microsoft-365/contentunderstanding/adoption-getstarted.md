---
title: 'Adopción de Microsoft SharePoint Syntex: Introducción'
description: Obtenga información sobre cómo usar e implementar SharePoint Syntex en su organización para ayudarle a resolver sus problemas empresariales.
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
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597063"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Adopción de Microsoft SharePoint Syntex: Introducción

Piense que los servicios de contenido inteligente disponibles en SharePoint Syntex tienen tres partes:

- **Descripción del contenido: cree** modelos de IA sin código para clasificar y extraer información del contenido para aplicar automáticamente metadatos para la detección y reutilización de conocimientos. Obtenga más información sobre [la comprensión del contenido](document-understanding-overview.md).
- **Procesamiento de contenido:** Automatice la captura, la ingesta y la categorización del contenido y optimice los procesos centrados en el contenido con Power Automate. Obtenga más información sobre [el procesamiento de contenido](form-processing-overview.md).
- **Cumplimiento de contenido:** Controle y administre el contenido para mejorar la seguridad y el gobierno con la integración en Microsoft Information Protection.

Con los nuevos servicios y capacidades de AI, puede crear aplicaciones de clasificación y comprensión de contenido directamente en el flujo de administración de contenido mediante SharePoint Syntex. Hay dos formas diferentes de comprender el contenido. El tipo de modelo que use se basa en el formato de archivo y el caso de uso:

| Procesamiento de formularios | Descripción de documentos |
|:-------|:-------|
| Creado a partir de la biblioteca de documentos. | Creado en el centro de contenido, parte de SharePoint Syntex. |
| Modelo creado en el generador de IA. | Modelo creado en interfaz nativa. |
| Se usa para formatos de archivo semiestructurados. | Se usa para formatos de archivo no estructurados. |
| Clasificador configurable. | Clasificador entrenable con extractores opcionales. |
| Restringido a una sola biblioteca. | Se puede aplicar a varias bibliotecas. |
| Train on PDF, JPG, PNG format, total 50 MB/500 pp. | Entrena en archivos PDF, Office o correo electrónico de 5 a 10, incluidos ejemplos negativos. |

Para obtener una comparación más completa de las capacidades, vea Diferencia entre la comprensión [de documentos y los modelos de procesamiento de formularios.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificar escenarios empresariales piloto para optimizar

Para prepararse para usar SharePoint Syntex en su organización, primero debe comprender los escenarios en los que será útil. El "por qué" ayuda a determinar qué modelo se necesita y cómo estructurar la organización en función de dónde se aplicará el modelo. Estos son algunos escenarios en los que la comprensión de documentos puede ayudar a su organización:

- **Procesamiento de contenido:** Procesar contratos, instrucciones de trabajo y otros documentos con formato. Admisión de formularios, entrenar al modelo para comprender y asignar los campos y, a continuación, ejecutar los formularios para recopilar automáticamente los datos. Para obtener más información, vea [Información general sobre el procesamiento de formularios.](form-processing-overview.md)
- **Análisis de facturas:** Extrae los detalles relevantes de tus facturas y asegúrate de que cumplen con la directiva o se están procesando correctamente.

Piense en las formas en que SharePoint Syntex puede ayudar a su organización:

- Automatizar procesos empresariales
- Mejorar la precisión de búsqueda
- Administrar el riesgo de cumplimiento

Cuando piense en qué escenarios empresariales debe tener en cuenta, haga las siguientes preguntas:

- ¿Resuelve un problema real?
- ¿Se usará ampliamente o tendrá un impacto general?
- ¿Se puede obtener?
- ¿Puede medir el éxito?

Priorizar escenarios en función del impacto y la facilidad de implementación. Haga que el área de enfoque inicial tenga un mayor impacto en escenarios que también se puedan implementar fácilmente. Des priorizar escenarios de menor impacto que son difíciles de implementar.

Use los siguientes escenarios de ejemplo para preguntar ideas sobre cómo puede usar SharePoint Syntex en su organización.

### <a name="scenario-track-data-from-invoices-with-form-processing"></a>Escenario: realizar un seguimiento de los datos de las facturas con el procesamiento de formularios

Por ejemplo, puede configurar un proceso con las características de SharePoint Syntex y Power Automate para realizar un seguimiento y supervisar las facturas.

1. Configurar una biblioteca para almacenar los documentos de factura.
1. Entrena al modelo para que reconozca los campos de los documentos.
1. Extraiga los campos que desea realizar un seguimiento en una lista.
1. Configure un flujo para notificarle eventos específicos, como:
    - Se agrega una nueva factura.
    - Una factura ha pasado de su fecha de vencimiento.
    - Una factura es para un importe que es mayor que el importe de aprobación automática.

![Seguimiento y supervisión de facturas con SharePoint Syntex y Power Automate](../media/content-understanding/process-invoices-flow.png)

Al automatizar este escenario, puede:

- Ahorre tiempo y dinero mediante la extracción automática de datos de las facturas en lugar de hacerlo manualmente.
- Reduzca los posibles errores y garantice un mejor cumplimiento mediante el uso de flujos de trabajo para comprobar facturas y notificarle cualquier problema.

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Escenario: realizar un seguimiento de la información de los contratos con la comprensión de documentos

Como otro ejemplo, puede configurar un proceso para identificar contratos que su empresa tiene con otras empresas o personas. Configure un modelo para extraer información clave de esos contratos, como el nombre del cliente, las tarifas, las fechas u otra información importante, y agregue la información a la biblioteca como campos que puede ver rápidamente. Aplique una etiqueta de retención en la biblioteca de documentos para asegurarse de que los contratos no se pueden eliminar antes de un período de tiempo específico para el cumplimiento adecuado de las normativas empresariales.

1. Comience en el centro de contenido y cree un nuevo modelo de comprensión de documentos para contratos.
1. Cargue documentos de ejemplo para ver ejemplos positivos y negativos y, a continuación, ejecute el aprendizaje para identificar documentos de contrato y revisar los resultados.
1. Entrena al extractor para identificar los campos de los contratos, como el nombre del cliente, la tarifa y la fecha, y luego prueba el extractor.
1. Cuando se complete el modelo, aplique el modelo a una biblioteca donde pueda cargar contratos.
1. Aplique una etiqueta de retención al campo fecha, de modo que los contratos se conserven en la biblioteca durante el período de tiempo necesario.

![Seguimiento y supervisión de contratos con SharePoint Syntex y etiquetas de retención](../media/content-understanding/process-contracts-flow.png)

Al automatizar este escenario, puede:

- Ahorre tiempo y dinero mediante la extracción automática de datos de los contratos en lugar de hacerlo manualmente.
- Asegúrese de un mejor cumplimiento mediante el uso de etiquetas de retención para garantizar que los contratos se conservan correctamente.

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Escenario: evitar riesgos con procesos de administración de registros, gobierno de documentos y cumplimiento basados en SharePoint Syntex

Reducir los riesgos es un objetivo común para la mayoría de las empresas. Es posible que necesite:

- Una mejor forma de proporcionar/aplicar el gobierno de la información en todo el espacio empresarial.
- Para mejorar el sistema de clasificación de documentos, correos electrónicos y otras formas de comunicación consideradas "registros" para proyectos.
- Auditar recibos, contratos, entre otros, para garantizar el cumplimiento de las directivas de la empresa.
- Para asegurarse de que los proyectos tienen toda la documentación necesaria para el cumplimiento.

Configure algunos procesos para el cumplimiento con SharePoint Syntex para capturar y clasificar adecuadamente, auditar y marcar documentos y formularios que necesitan un mejor gobierno. Puede confiar en SharePoint Syntex para clasificar automáticamente el contenido en lugar de depender de los usuarios finales para etiquetar manualmente o del equipo de cumplimiento para aplicar manualmente reglas de gobierno y archivado. Además, puede habilitar una experiencia de búsqueda simplificada, administrar volúmenes de datos, aplicar directivas de administración y retención de registros, garantizar el cumplimiento y procedimientos recomendados de archivado y depuración.

Al automatizar este escenario, puede sentirse seguro de que:

- Se mantiene el cumplimiento y se reduce el riesgo.
- La taxonomía y la administración de registros se aplican de forma coherente y precisa.
- Los volúmenes de contenido se controlan.
- Los empleados pueden descubrir fácilmente la información correcta en el contexto correcto.

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Escenario: capturar información de documentos inaccesibles anteriormente

La mayoría de las organizaciones tienen grandes repositorios de documentos legales, directivas, contratos, documentos de recursos humanos y directrices de gobierno. Extrae estos almacenes de datos para extraer información valiosa como: proyectos, sectores, temas, personas, áreas geográficas, entre otros.

Por ejemplo, un director de recursos humanos debe tener acceso rápidamente a todos los documentos de recursos humanos, incluidos los currículums, las directivas de RECURSOS humanos y otros formularios. Además, desean identificar rápidamente la información necesaria de los currículums y otros documentos relacionados con RRHH sin realizar un control manual de los documentos. Están buscando una solución que les permita encontrar rápidamente la información que necesitan sin tener que buscar manualmente miles de currículums, directivas de RRHH y otra documentación que se puedan propagar por varios sitios.

Al automatizar este escenario, puede:

- Desbloquear conocimientos del contenido digital.
- Clasificar directivas de recursos humanos, currículos, documentos de ventas, planos técnicos, planes de cuenta y extraer información.
- Busque rápidamente la información o el documento correctos que está buscando.
- Obtenga acceso instantáneo a la información más reciente.
- Reducir los tiempos de búsqueda.

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a>Escenario: mejorar el procesamiento de datos para proporcionar información & análisis

Por ejemplo, una compañía farmacéutica podría usar SharePoint Syntex para extraer información de documentos de la FDA para responder a las preguntas que tienen sus líderes. Tener las respuestas más fácilmente accesibles puede reducir el tiempo necesario para producir estas respuestas y aumentar la disponibilidad de datos para generar respuestas más precisas a las preguntas de liderazgo.

Por ejemplo, un jefe de proyecto debe proporcionar rápidamente respuestas a preguntas relacionadas con el producto de mi equipo de liderazgo. Deben encontrar información y métricas relacionadas con las consultas en un panel consolidado. Buscan una solución que extraiga la información que necesitan de etiquetas de productos, panfletos de productos y otros materiales y genere un informe consolidado que puedan usar al informar a su equipo de liderazgo.

Al automatizar este escenario, puede:

- Reduzca el tiempo para producir respuestas.
- Aumentar la disponibilidad de los datos.
- Proporcionar respuestas más precisas.

### <a name="scenario-automate-order-processing"></a>Escenario: Automatizar el procesamiento de pedidos

Con SharePoint Syntex, puede reducir el tiempo de procesamiento manual de los pedidos de clientes. Por ejemplo, puede cargar pedidos de fax, correo electrónico o papel en SharePoint mediante el procesamiento ocr y, a continuación, extraer los metadatos de esos pedidos para que pueda cumplirlos mediante procesos automatizados.

Por ejemplo, un administrador de cadena de suministro quiere reducir los errores causados por la entrada de datos manual. Quieren evitar la revisión manual y la entrada de datos de los pedidos de clientes entrantes (papel, fax o correo electrónico) para reducir los errores que se producen en sus sistemas empresariales. Quieren una solución que aplique la inteligencia artificial y las técnicas de aprendizaje automático para validar la información de los pedidos entrantes, extraer datos básicos y insertarlo automáticamente en su sistema ERP, para el cumplimiento y la conciliación de pedidos.

Al automatizar este escenario, puede asegurarse de que:

- Aumenta la precisión del pedido y el envío.
- Se reducen las tarifas o penalizaciones asociadas a errores de pedido o envío.
- Los retrasos en la facturación o los pagos disminuyen.
- Se reducen los costos de personal.

### <a name="scenario-simplify-visa-renewal-process"></a>Escenario: Simplificar el proceso de renovación de visas

SharePoint Syntex puede ayudarle a automatizar avisos y renovaciones para la información clave del contrato. Por ejemplo, un director de recursos humanos debe asegurarse de que los visados de los empleados estén actualizados o renovados a tiempo. Quieren ofrecer a los usuarios un proceso sencillo e intuitivo para actualizar sus Visas. Necesitan una solución que extraiga las fechas de renovación de los contratos y envíe automáticamente avisos a los empleados cuando se acercan las fechas de renovación.

Al automatizar este escenario, puede asegurarse de que:

- Se reducen los niveles de incumplimiento.
- Se reduce el número de avisos manuales.
- Se reduce el número de multas por incumplimiento.

## <a name="identify-roles--responsibilities"></a>Identificar roles & responsabilidades

Determine who in your organization will build and manage the models? Los siguientes roles pueden estar implicados:

| Administrador de SharePoint/Knowledge | Administrador de Power Platform | Administrador de conocimientos | Propietario del modelo |
|:-------|:-------|:-------|:-------|
| Rol AAD| Rol AAD | Rol AAD | Expertos: |
| Configurar el procesamiento del formulario | Configurar el entorno de servicio de datos común para el procesamiento de formularios | Recopilar casos de uso | Recopilar casos de uso empresarial |
| Administrar centros de contenido y permisos| Comprar y asignar créditos AIB | Establecer procedimientos recomendados y revisar análisis de modelos | Crear y aplicar modelos |

El administrador de conocimientos, el propietario del proceso de negocio y el propietario del modelo de contenido crean modelos de ejemplo y la adopción de campeones en la organización.
Otros que pueden estar implicados: administrador de cumplimiento, administradores de taxonomía.

¿Dónde crearán y aplicarán los modelos? ¿Hay procesos o repositorios existentes que podrían mejorarse?

- Procesamiento de formularios: decida qué sitios recibirán acción de procesamiento de formularios.
- Descripción del documento: puede crear varios centros de contenido para distintas áreas de negocio.

## <a name="strategic-positioning"></a>Posicionamiento estratégico

Trabaje con las partes interesadas para asegurarse de que están alineados en la estrategia para usar SharePoint Syntex. Investigue y proporcione los siguientes recursos para ayudarle con este posicionamiento:

- Resultados empresariales:
  - Posibles resultados fiscales
  - Posibles resultados de agilidad
  - Plantilla de resultados empresariales
- Stakeholders/Exec sponsor buy-in/alignment
  - Barajas de casos profesionales
  - Modelos financieros
  - Preparación de la empresa: cultura

## <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Identificar las partes interesadas del proyecto.

|Función |Responsibilities |Department |
|:-------|:-------|:--------|
| Patrocinadores ejecutivos   | Comunicar la visión y los valores de alto nivel a la empresa   |  Liderazgo ejecutivo   |
| Clientes potenciales del proyecto | Supervisar todo el proceso de ejecución e implementación del inicio | Administración de proyectos |
| Administradores de conocimientos| Crear y administrar los centros de contenido | TI u otro departamento|
| Administradores de contenido y propietarios de modelos| Recopilar casos de uso y crear y aplicar modelos | Cualquier departamento|
| Expertos: | Ayudar a evangelizar y administrar el tratamiento de las objeciones | Cualquier departamento (personal) |
| Administrador de inquilinos | Configurar las opciones de nivel de inquilino | Departamento de TI|
| Administrador de Power Platform| Configurar un entorno de servicios de datos común | Departamento de TI|

> [!Note]
> Aunque se recomienda que cada uno de estos roles se cumpla a lo largo de la implementación, es posible que no necesite todos ellos para empezar con la solución identificada.

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
    - Diseñe el proceso de definición, creación, administración.

## <a name="engage-your-organization"></a>Interactuar con su organización

1. Identificar a los poseedores de participación, confirmar escenarios y desarrollar un plan de proyecto.
1. Configure la configuración y aplique licencias.
1. Comenzar a concienciar y entrenar: reclutar a los campeones.
1. Roll out in stages.  
1. Recopilar comentarios e iterar.
1. A medida que aumenta el uso, planee los créditos de AI Builder según sea necesario.
