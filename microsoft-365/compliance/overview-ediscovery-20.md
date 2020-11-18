---
title: Información general sobre la solución de exhibición de documentos electrónicos avanzada en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: En este artículo se proporciona una introducción a la exhibición avanzada de documentos electrónicos en Microsoft 365, una herramienta para investigaciones internas y externas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6225411bcd3051c19e22fcb205cc7dee92f99f82
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131033"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a>Información general sobre la solución de exhibición de documentos electrónicos avanzada en Microsoft 365

La solución Advanced eDiscovery de Microsoft 365 se basa en las capacidades existentes de eDiscovery y de análisis en Office 365. Esta nueva solución, denominada *exhibición avanzada* de documentos electrónicos, proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de la organización. También permite a los equipos jurídicos administrar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores involucrados en un caso. 

> [!NOTE]
> EDiscovery avanzado requiere una suscripción de Office 365 o Microsoft 365 E5 Enterprise. Para obtener más información sobre las licencias de eDiscovery avanzadas, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-ediscovery).

## <a name="alignment-with-edrm"></a>Alineación con EDRM

El flujo de trabajo integrado de eDiscovery avanzado se alinea con el proceso de eDiscovery descrito por el modelo de referencia de detección electrónica (EDRM). 

![Modelo de referencia de detección electrónica (EDRM)](../media/EDRMv1.png)

(Origen de la imagen por cortesía de edrm.net. La imagen de origen estaba disponible en la licencia no desported de Creative Commons Atribution 3,0.)

En un nivel alto, a continuación se muestra cómo la exhibición avanzada de documentos electrónicos admite el flujo de trabajo EDRM:

- **Determinación.** Después de identificar las posibles personas de interés en una investigación, puede agregarlas como custodios (también denominadas *custodios de datos*, ya que pueden tener información relevante para la investigación) a un caso avanzado de eDiscovery. Después de identificar a los custodios y agregarlos a un caso, puede preservar, recopilar, revisar y analizar fácilmente los datos de las privaciones asociados.

- **Buena.** Para preservar y proteger los datos relevantes para una investigación, eDiscovery avanzado le permite realizar una retención legal en los orígenes de datos asociados con los custodios en un caso. También puede poner los datos no coprivate en suspensión (normalmente recursos de grupo compartidos, como sitios de SharePoint o canales de Teams compartidos). EDiscovery avanzado también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de retención legal a los custodios y realizar un seguimiento de sus confirmaciones.

- **Colección.** Una vez que haya identificado (y conservado) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integrada en eDiscovery avanzado para buscar y recopilar datos en directo de los orígenes de datos de Private (y de los orígenes de datos que no sean de privación, si procede) que puedan ser relevantes para el caso.

- **Procesar.** Una vez que haya recopilado todos los datos relevantes para el caso, el siguiente paso es procesarlo para la revisión y el análisis adicionales. En la exhibición avanzada de documentos electrónicos, los datos locales identificados en la fase de recopilación se copian en una ubicación de almacenamiento de Azure (denominada *conjunto de revisión*), que proporciona una vista estática de los datos de caso.

- **Comprueba.** Una vez agregados los datos a un conjunto de revisión, puede ver documentos específicos y ejecutar consultas adicionales en el conjunto de revisión para reducir los datos a los documentos más relevantes. También puede anotar y etiquetar documentos específicos.

- **Analice.** EDiscovery avanzado proporciona un eficaz conjunto de herramientas de análisis integradas que le ayudarán a deseleccionar de manera inteligente los datos irrelevantes del conjunto de revisión, lo que le ahorra los costos de revisión legal mediante la reducción eficaz del volumen de datos relevantes para la producción.

- **Producción** y **presentación.** Cuando esté listo, puede exportar documentos de un conjunto de revisiones para revisión legal. Puede exportar documentos en su formato especificado por el EDRM para que puedan importarse en aplicaciones de revisión de terceros.

## <a name="advanced-ediscovery-architecture"></a>Arquitectura avanzada de eDiscovery

Este es un diagrama de arquitectura de eDiscovery avanzado que muestra el flujo de trabajo de un extremo a otro en un entorno de un solo geográfico y un entorno multigeográfico. El flujo de datos de un extremo a otro está alineado con el EDRM.

[![Póster de modelos: arquitectura avanzada de exhibición de documentos electrónicos en Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Ver como imagen](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Descargar como archivo PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Descargar como archivo de Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

Para obtener más información acerca del flujo de trabajo de un extremo a otro en la exhibición avanzada de documentos electrónicos, vea este [vídeo de Microsoft](https://go.microsoft.com/fwlink/?linkid=2066133).

En las secciones siguientes se describe cada paso del flujo de trabajo integrado en la exhibición avanzada de documentos electrónicos. En la siguiente captura de pantalla se muestra la ficha **información general** de un caso denominado *2020.11.03-contoso v. fabrikam*.

![Pestañas en el flujo de trabajo de eDiscovery avanzado integrado](../media/AeD-Case-Screenshot1.png)

## <a name="managing-custodians-and-non-custodial-data-sources"></a>Administración de custodios y orígenes de datos que no son de privación

Use la pestaña **orígenes de datos** para agregar y administrar las personas que ha identificado como personas de interés en el caso y otros orígenes de datos que no se pueden asociar con un custodio. Cuando se agregan custodios o fuentes de datos que no son de privación, puede realizar acciones rápidamente, como poner en retención legal en custodios y orígenes de datos que no son de privación, comunicarse con custodios y buscar en los orígenes de datos que no sean de custodia y recopilar contenido que sea relevante para el caso. A medida que avanza el caso, es fácil agregar custodios nuevos o fuentes de datos que no sean de privación o liberarlos del caso. Para obtener más información, consulte [work with custodios in Advanced eDiscovery](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Administración de notificaciones de retención legal

Use la pestaña **comunicaciones** para administrar el proceso de comunicación con los custodios en el caso. Un aviso de suspensión legal instruye a los custodios para que conserven el contenido relevante para el caso. Los equipos jurídicos deben realizar un seguimiento de los avisos recibidos, leídos y confirmados por los custodios. El flujo de trabajo de comunicaciones en eDiscovery avanzado permite crear y enviar notificaciones iniciales, recordatorios, avisos de versión y escalamientos si los custodios no reconocen una notificación de retención. Para obtener más información, consulte [trabajar con comunicaciones en la exhibición avanzada de](managing-custodian-communications.md)documentos electrónicos.

## <a name="managing-content-preservation"></a>Administración de la conservación de contenido

Cuando agrega un custodio a un caso, puede poner una retención en los datos de Private. Use la pestaña **suspender** para administrar la suspensión creada al agregar custodios y administrar otras retenciones legales asociadas con el caso; por ejemplo, puede identificar y poner una retención en orígenes de datos que no sean de Private. También puede editar cualquier suspensión en el caso y convertirlo en una retención basada en consulta para conservar solo el contenido que coincida con la consulta. Por ejemplo, puede Agregar un intervalo de fechas a la suspensión para que solo se conserve el contenido creado en un intervalo de fechas específico. También puede obtener estadísticas de contenido que está en suspensión, quitar la retención después de que ya no sea relevante para el caso o eliminarla. Para obtener más información, consulte [Administrar suspensiones en EDiscovery avanzado](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indización de datos del custodio

Cuando se agrega un custodio y los orígenes de datos Private correspondientes a un caso, un proceso denominado *indización avanzada* reindiza los elementos parcialmente indizados de un origen de datos de custodios. Esto permite que el contenido de apoyo como imágenes, tipos de archivo no admitidos y otro contenido no indexado se pueda buscar por completo al ejecutar búsquedas para recopilar datos en el caso. Use la ficha **procesamiento** para supervisar el estado de la indización avanzada y corregir los errores de procesamiento mediante un proceso denominado *corrección de errores*. Para obtener más información, vea [corregir errores de procesamiento en la exhibición avanzada de](processing-data-for-case.md)documentos electrónicos.

## <a name="collecting-case-data"></a>Recopilar datos de casos

Use la ficha **búsquedas** para crear búsquedas para buscar en los orígenes de datos de la custodia y no Private de los contenidos relevantes para el caso. Puede crear y ejecutar búsquedas basadas en consultas (usando palabras clave y condiciones) para identificar un conjunto de mensajes de correo electrónico y documentos relevantes para el caso y que desee revisar y analizar con más detalle en los siguientes pasos del flujo de trabajo de eDiscovery. Puede crear una o más búsquedas asociadas con el caso. También puede usar la herramienta de búsqueda para obtener una vista previa de los documentos de ejemplo y ver estadísticas de búsqueda para ayudarle a refinar y mejorar los resultados de la búsqueda. Una vez que haya buscado y recopilado todos los datos relevantes para el caso, puede Agregar los resultados de la búsqueda a un conjunto de revisión para la revisión, el análisis y la selección adicionales. Para obtener más información, vea [recopilar datos para un caso en EDiscovery avanzado](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzing-case-data"></a>Revisión y análisis de datos de casos

Use la ficha de **Review sets** para revisar y analizar el contenido que ha recopilado desde el sistema activo y que se ha agregado a un conjunto de revisión. Un *conjunto de revisión* es una colección estática de los datos (es decir, una copia sin conexión de datos) de los datos de Private (y, si procede, datos que no son de Private) que recopiló en la fase anterior del flujo de trabajo de eDiscovery. Cuando se agregan los resultados de la búsqueda a un conjunto de revisión, se desencadena un proceso para extraer los archivos de los contenedores, extraer los metadatos y extraer el texto. Cuando se completa este proceso, el sistema crea un nuevo índice de todos los datos recopilados por los custodios y los agrega al conjunto de revisión. Una vez que los datos se agregan al conjunto de revisión, puede ejecutar más consultas para acotar los datos de mayúsculas y minúsculas, ver datos como texto o en el formato de archivo nativo, y anotar, censurar y etiquetar documentos en el conjunto de revisión. También puede realizar análisis avanzados, como la identificación de la duplicación de documentos, el procesamiento de correo electrónico y los temas. Una vez que haya seleccionado los datos solo para lo que sea relevante para el caso, puede descargar los documentos directamente o exportarlos junto con los metadatos de archivo, las anotaciones y cualquier etiqueta. Para más información, vea:

- [Ver documentos de un conjunto de revisión](view-documents-in-review-set.md)

- [Consultar los datos de un conjunto de revisión](review-set-search.md)

- [Etiquetar documentos en un conjunto de revisión](tagging-documents.md)

- [Analizar datos en un conjunto de revisión](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Exportar datos para revisión y presentación

Después de exportar los datos de un conjunto de revisión, use la pestaña **exportaciones** para administrar un trabajo de exportación y descargar datos de un conjunto de revisión. Al exportar un conjunto de revisión, los datos se cargan en una ubicación de almacenamiento de Azure proporcionada por Microsoft (o en una ubicación de almacenamiento de Azure administrada por la organización). Una vez que se carga en Azure, es posible descargarla en un equipo local. Puede obtener la clave de acceso de almacenamiento necesaria para descargar los datos exportados en la ficha **Exports** . Para obtener más información, vea [exportar datos de casos en EDiscovery avanzado](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Administración de trabajos

Use la ficha **trabajos** para supervisar procesos de ejecución prolongada para las tareas relacionadas con casos que haya iniciado. Algunos ejemplos de trabajos son los relacionados con la reindización, la búsqueda y la exportación de datos de casos. Por ejemplo, si crea una búsqueda en la ficha **búsquedas** que incluye muchos orígenes de datos, el estado de este proceso de búsqueda se mostrará en la ficha **trabajos** . Para obtener más información, consulte [administrar trabajos en EDiscovery avanzado](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configuración de los casos

Use la pestaña **configuración** para establecer la configuración de casos. Esto incluye agregar miembros a un caso, cerrar o eliminar un caso y configurar las opciones de búsqueda y análisis.
