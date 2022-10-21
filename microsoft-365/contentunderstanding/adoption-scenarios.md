---
title: Escenarios y casos de uso para Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris
ms.date: ''
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
ms.localizationpriority: medium
description: Busque escenarios empresariales sobre cómo usar Microsoft Syntex en su organización.
ms.openlocfilehash: a43231e268e69a74cdc0bbc35df2cdd24d9e0d37
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660915"
---
# <a name="scenarios-and-use-cases-for-microsoft-syntex"></a>Escenarios y casos de uso para Microsoft Syntex

Use los escenarios de ejemplo siguientes para preguntar ideas sobre cómo puede usar Microsoft Syntex en su organización.

- [Escenario: Seguimiento de la información de las facturas mediante el modelo de procesamiento estructurado de documentos](adoption-scenarios.md#scenario-track-information-from-invoices-by-using-the-structured-document-processing-model)
- [Escenario: Seguimiento de la información de los contratos mediante el modelo de procesamiento de documentos no estructurado](adoption-scenarios.md#scenario-track-information-from-contracts-by-using-the-unstructured-document-processing-model)
- [Escenario: Evitar riesgos con la administración de registros, la gobernanza de documentos y los procesos de cumplimiento basados en Syntex](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-syntex)
- [Escenario: Captura de información de documentos inaccesibles anteriormente](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [Escenario: Mejora del procesamiento de datos para proporcionar información y análisis](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [Escenario: Automatización del procesamiento de pedidos](adoption-scenarios.md#scenario-automate-order-processing)
- [Escenario: Simplificación del proceso de renovación de visados](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-information-from-invoices-by-using-the-structured-document-processing-model"></a>Escenario: Seguimiento de la información de las facturas mediante el modelo de procesamiento estructurado de documentos

Por ejemplo, puede configurar un proceso mediante las características de Syntex y Power Automate para realizar un seguimiento y supervisar las facturas.

1. Configure una biblioteca para almacenar los documentos de factura.
2. Entrenar el modelo para reconocer campos en los documentos.
3. Extraiga los campos de los que desea realizar un seguimiento en una lista.
4. Configure un flujo para notificarle eventos específicos, como:
    - Se agrega una nueva factura.
    - Una factura ha superado su fecha de vencimiento.
    - Una factura es para un importe mayor que el importe de aprobación automática.

![Realice un seguimiento y supervise las facturas con Syntex y Power Automate.](../media/content-understanding/process-invoices-flow.png)

Al automatizar este escenario, puede hacer lo siguiente:

- Ahorre tiempo y dinero mediante la extracción automática de datos de las facturas en lugar de hacerlo manualmente.
- Reduzca los posibles errores y garantice un mejor cumplimiento mediante flujos de trabajo para comprobar las facturas y notificarle cualquier problema.

## <a name="scenario-track-information-from-contracts-by-using-the-unstructured-document-processing-model"></a>Escenario: Seguimiento de la información de los contratos mediante el modelo de procesamiento de documentos no estructurado

Como otro ejemplo, puede configurar un proceso para identificar los contratos que su empresa tiene con otras empresas o personas. Configure un modelo para extraer información clave de esos contratos, como el nombre del cliente, las tarifas, las fechas u otra información importante, y agregue la información a la biblioteca como campos que puede ver rápidamente. Aplique una etiqueta de retención en la biblioteca de documentos para asegurarse de que los contratos no se pueden eliminar antes de un período de tiempo específico para el cumplimiento adecuado de las regulaciones empresariales.

1. Comience en el centro de contenido y cree un nuevo modelo de procesamiento de documentos no estructurado para contratos.
2. Cargue documentos de ejemplo para ejemplos positivos y negativos y, a continuación, ejecute el entrenamiento para identificar documentos de contrato y revisar los resultados.
3. Entrene el extractor para identificar los campos de los contratos, como el nombre del cliente, la cuota y la fecha, y, a continuación, pruebe el extractor.
4. Una vez completado el modelo, aplique el modelo a una biblioteca donde pueda cargar contratos.
5. Aplique una etiqueta de retención al campo de fecha para que los contratos se conserven en la biblioteca durante el tiempo necesario.

![Realice un seguimiento y supervise los contratos con Syntex y las etiquetas de retención.](../media/content-understanding/process-contracts-flow.png)

Al automatizar este escenario, puede hacer lo siguiente:

- Ahorre tiempo y dinero mediante la extracción automática de datos de los contratos en lugar de hacerlo manualmente.
- Asegúrese de un mejor cumplimiento mediante el uso de etiquetas de retención para asegurarse de que los contratos se conservan correctamente.

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-syntex"></a>Escenario: Evitar riesgos con la administración de registros, la gobernanza de documentos y los procesos de cumplimiento basados en Syntex

Reducir los riesgos es un objetivo común para la mayoría de las empresas. Es posible que necesite lo siguiente:

- Una mejor manera de proporcionar o aplicar la gobernanza de la información en todo el inquilino.
- Mejorar el sistema de clasificación de documentos, correos electrónicos y otras formas de comunicación consideradas "registros" para proyectos.
- Para auditar recibos, contratos, etc., para garantizar el cumplimiento de las directivas de la empresa.
- Para asegurarse de que los proyectos tienen toda la documentación necesaria para el cumplimiento.

Configure algunos procesos para que el cumplimiento con Syntex capture y clasifique, audite y marque correctamente documentos y formularios que necesiten una mejor gobernanza. Puede confiar en Syntex para clasificar automáticamente el contenido en lugar de confiar en que los usuarios finales etiqueten manualmente o que el equipo de cumplimiento aplique manualmente reglas de gobernanza y archivado. Además, puede habilitar una experiencia de búsqueda simplificada, administrar volúmenes de datos, aplicar directivas de administración y retención de registros, garantizar el cumplimiento y procedimientos recomendados de archivado y purga.

Al automatizar este escenario, puede sentirse seguro de que:

- Se confirma el cumplimiento y se reduce el riesgo.
- La taxonomía y la administración de registros se aplican de forma coherente y precisa.
- Los volúmenes de contenido se controlan.
- Los empleados pueden descubrir fácilmente la información adecuada en el contexto adecuado.

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Escenario: Captura de información de documentos inaccesibles anteriormente

La mayoría de las organizaciones tienen grandes repositorios de documentos legales, directivas, contratos, documentos de RR. HH. y directrices de gobernanza. Extraiga estos almacenes de datos para extraer información valiosa como: proyectos, sectores, temas, personas, áreas geográficas, etc.

Por ejemplo, un director de RR. HH. debe acceder rápidamente a todos los documentos de RR. HH., incluidos los currículos, las directivas de RR. HH. y otros formularios. Y quieren identificar rápidamente la información necesaria de los currículos y otros documentos relacionados con RR. HH. sin realizar un tamado manual a través de los documentos. Buscan una solución que les permita encontrar rápidamente la información que necesitan sin tener que examinar manualmente miles de currículos, directivas de RR. HH. y otra documentación que se pueda distribuir entre varios sitios.

Al automatizar este escenario, puede hacer lo siguiente:

- Desbloquea conocimientos del contenido digital.
- Clasifique las directivas de RR. HH., las reanudaciones, los documentos de ventas, los planos técnicos y los planes de cuenta y extraiga información.
- Encuentre rápidamente la información o el documento correctos que está buscando.
- Obtenga acceso instantáneo a la información más reciente.
- Reducir los tiempos de búsqueda.

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>Escenario: Mejora del procesamiento de datos para proporcionar información y análisis

Por ejemplo, una empresa farmacéutica podría usar Syntex para extraer información de documentos de la FDA para responder a preguntas que sus líderes tienen. Tener las respuestas más fácilmente accesibles puede reducir el tiempo necesario para generar estas respuestas y aumentar la disponibilidad de los datos para generar respuestas más precisas a las preguntas de liderazgo.

Por ejemplo, un administrador de proyectos debe proporcionar rápidamente respuestas a las preguntas relacionadas con el producto de mi equipo directivo. Deben encontrar información y métricas relacionadas con las consultas en un panel consolidado. Buscan una solución que extraiga la información que necesitan de etiquetas de producto, folletos de productos y otros materiales y genere un informe consolidado que puedan usar al informar a su equipo directivo.

Al automatizar este escenario, puede hacer lo siguiente:

- Reduzca el tiempo para generar respuestas.
- Aumentar la disponibilidad de los datos.
- Proporcione respuestas más precisas.

## <a name="scenario-automate-order-processing"></a>Escenario: Automatización del procesamiento de pedidos

Con Syntex, puede reducir el tiempo de procesamiento manual de pedidos del cliente. Por ejemplo, puede cargar pedidos de fax, correo electrónico o papel en SharePoint mediante el procesamiento de OCR y, a continuación, extraer los metadatos de esos pedidos para que pueda cumplirlos mediante procesos automatizados.

Por ejemplo, un administrador de la cadena de suministro quiere reducir los errores causados por la entrada manual de datos. Quieren evitar la revisión manual y la entrada de datos de los pedidos de clientes entrantes (papel, fax o correo electrónico) para reducir los errores que se producen en sus sistemas empresariales. Quieren una solución que aplique técnicas de inteligencia artificial y aprendizaje automático para validar la información de pedidos entrantes, extraer datos principales e insertarlos automáticamente en su sistema ERP, para la conciliación y el cumplimiento de pedidos.

Al automatizar este escenario, puede asegurarse de que:

- La precisión de pedidos y envíos aumenta.
- Se reducen las tarifas o penalizaciones asociadas a errores de pedido o envío.
- Los retrasos en la facturación o los pagos disminuyen.
- Se reducen los costos de personal.

## <a name="scenario-simplify-visa-renewal-process"></a>Escenario: Simplificación del proceso de renovación de visados

Syntex puede ayudarle a automatizar recordatorios y renovaciones para obtener información clave del contrato. Por ejemplo, un director de RR. HH. debe asegurarse de que los visados de los empleados estén actualizados o renovados a tiempo. Quieren dar a las personas un proceso sencillo e intuitivo para actualizar sus visas. Necesitan una solución que extraiga las fechas de renovación de los contratos y envíe automáticamente recordatorios a los empleados cuando se aproximan sus fechas de renovación.

Al automatizar este escenario, puede asegurarse de que:

- Se reducen los niveles de incumplimiento.
- Se reduce el número de avisos manuales.
- Se reduce el número de multas por incumplimiento.

## <a name="see-also"></a>Vea también

[Introducción a la adopción de Microsoft Syntex](adoption-getstarted.md)

[Administrar contratos con una solución de Microsoft 365](solution-manage-contracts-in-microsoft-365.md)
