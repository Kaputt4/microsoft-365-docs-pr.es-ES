---
title: ¿Qué es Inteligencia contra amenazas de Microsoft Defender (TI de Defender)?
description: En este artículo de información general, obtenga información sobre las características principales que se incluyen con Inteligencia contra amenazas de Microsoft Defender (TI de Defender).
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: overview
ms.date: 08/02/2022
ms.custom: template-overview
ms.openlocfilehash: a71723192f84b75468c0556d44bca4ca4bf0290f
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "67108468"
---
# <a name="what-is-microsoft-defender-threat-intelligence-defender-ti"></a>¿Qué es Inteligencia contra amenazas de Microsoft Defender (TI de Defender)?

Inteligencia contra amenazas de Microsoft Defender (Ti de Defender) es una plataforma que simplifica los flujos de trabajo de analistas de inteligencia sobre amenazas cibernética, búsqueda de amenazas, búsqueda de amenazas y evaluación de amenazas al realizar análisis de infraestructura de amenazas y recopilar información sobre amenazas. Los analistas dedican una cantidad significativa de tiempo a la detección, recopilación y análisis de datos, en lugar de centrarse en lo que realmente ayuda a su organización a defenderse a sí mismos, derivando información sobre los actores a través del análisis y la correlación.

A menudo, los analistas deben ir a varios repositorios para obtener los conjuntos de datos críticos que necesitan para evaluar un dominio, host o dirección IP sospechosos. Los datos DNS, la información de WHOIS, el malware y los certificados SSL proporcionan un contexto importante a los indicadores de riesgo (IOC), pero estos repositorios están ampliamente distribuidos y no siempre comparten una estructura de datos común, lo que dificulta garantizar que los analistas tengan todos los datos pertinentes necesarios para realizar una evaluación adecuada y oportuna de la infraestructura sospechosa.

Interactuar con estos conjuntos de datos puede ser complicado y la dinamización entre estos repositorios requiere mucho tiempo, lo que agota los recursos de los grupos de operaciones de seguridad que necesitan constantemente volver a priorizar sus esfuerzos de respuesta.

Los analistas de inteligencia sobre amenazas cibernéticas tienen dificultades para equilibrar una amplitud de ingesta de inteligencia sobre amenazas con el análisis de qué inteligencia de amenazas representa las mayores amenazas para su organización o sector.

En la misma amplitud, los analistas de inteligencia de vulnerabilidades luchan por correlacionar su inventario de activos con información de CVE para priorizar la investigación y corrección de las vulnerabilidades más críticas asociadas a su organización.

El objetivo de Microsoft es volver a imaginar el flujo de trabajo del analista mediante el desarrollo de una plataforma, Defender TI, que agrega y enriquece orígenes de datos críticos y muestra los datos en una interfaz innovadora y fácil de usar para correlacionar cuando los indicadores están vinculados a artículos y vulnerabilidades, encadenar la infraestructura junto con indicadores de riesgo (IOC) y colaborar en investigaciones con otros usuarios con licencia de Ti de Defender dentro de su inquilino. Con las organizaciones de seguridad que realizan una cantidad cada vez mayor de inteligencia y alertas dentro de su entorno, es importante tener una plataforma de inteligencia de análisis de amenazas & que permita evaluaciones precisas y oportunas de las alertas.

A continuación se muestra una captura de pantalla de la página principal de Inteligencia sobre amenazas de Defender TI. Los analistas pueden examinar rápidamente los nuevos artículos destacados, así como comenzar su trabajo de recopilación de inteligencia, evaluación de prioridades, respuesta a incidentes y búsqueda mediante la realización de una búsqueda de palabras clave, artefactos o CVE-ID.

![Captura de pantalla de Edge de información general de TI](media/tiOverviewEdgeScreenshot.png)

## <a name="defender-ti-articles"></a>Artículos de TI de Defender
Los artículos son narraciones de Microsoft que proporcionan información sobre los actores de amenazas, las herramientas, los ataques y las vulnerabilidades. Los artículos y destacados de TI de Defender no son entradas de blog sobre inteligencia sobre amenazas; mientras resumen diferentes amenazas, también se vinculan a contenido accionable e indicadores clave de riesgo para ayudar a los usuarios a tomar medidas. Al incluir esta información técnica en los resúmenes de amenazas, permitimos a los usuarios realizar un seguimiento continuo de los actores de amenazas, las herramientas, los ataques y las vulnerabilidades a medida que cambian.

## <a name="featured-articles"></a>Artículos destacados

La sección de artículo destacado de la página principal de Inteligencia sobre amenazas de TI de Defender (justo debajo de la barra de búsqueda) muestra el contenido destacado de Microsoft:

![Artículos destacados de información general de TI](media/tiOverviewFeaturedArticles.png)

Al hacer clic en el artículo, se le lleva al contenido del artículo subyacente. La sinopsis del artículo proporciona al usuario un conocimiento rápido del artículo. En la llamada a Indicadores se muestra cuántos indicadores de TI públicos y de Defender están asociados con el artículo.

![Artículo destacado de información general de TI](media/tiOverviewFeaturedArticle.png)

## <a name="articles"></a>Artículos

Todos los artículos (incluidos los artículos destacados) se enumeran en la sección Artículos de la página principal de Inteligencia sobre amenazas de TI de Microsoft Defender, ordenada por su fecha de creación (descendente):

![Artículos de información general de TI](media/tiOverviewArticles.png)

## <a name="article-descriptions"></a>Descripciones de artículos

La sección de descripción de la pantalla de detalles del artículo contiene información sobre el ataque o el atacante perfilado. El contenido puede variar desde muy corto (en el caso de los boletines de OSINT) o bastante largo (para informes de forma larga, especialmente cuando Microsoft ha aumentado el informe con contenido). Las descripciones más largas pueden contener imágenes, vínculos al contenido subyacente, vínculos a búsquedas dentro de TI de Defender, fragmentos de código del atacante y reglas de firewall para bloquear el ataque:

![Descripción del artículo información general de TI](media/tiOverviewArticleDescription.png)

## <a name="public-indicators"></a>Indicadores públicos

La sección de indicadores públicos de la pantalla muestra los indicadores publicados anteriormente relacionados con el artículo. Los vínculos de los indicadores públicos llevan uno a los datos de TI de Defender subyacentes o a los orígenes externos pertinentes (por ejemplo, VirusTotal para hashes).

![Información general sobre TI Artículo Indicadores públicos](media/tiOverviewArticlePublicIndicators.png)

## <a name="defender-ti-indicators"></a>Indicadores de TI de Defender

En la sección Indicadores de TI de Defender se tratan los indicadores que el equipo de investigación de Defender TI ha encontrado y agregado a los artículos.

Estos vínculos también se difunden en los datos de TI de Defender pertinentes o en el origen externo correspondiente.

![Artículo de información general de TI: Indicadores de TI de Defender](media/tiOverviewArticleDefenderTiIndicators.png)

## <a name="vulnerability-articles"></a>Artículos sobre vulnerabilidades

Defender TI ofrece búsquedas de CVE-ID para ayudar a los usuarios a identificar información crítica sobre el CVE. Las búsquedas de CVE-ID dan como resultado artículos de vulnerabilidad.

Los artículos sobre vulnerabilidades proporcionan un contexto clave detrás de los CVE de interés. Cada artículo contiene una descripción del CVE, una lista de componentes afectados, procedimientos y estrategias de mitigación personalizados, artículos de inteligencia relacionados, referencias en charlas de Deep & Dark Web y otras observaciones clave. Estos artículos proporcionan contexto más profundo e información útil detrás de cada CVE, lo que permite a los usuarios comprender más rápidamente estas vulnerabilidades y mitigarlas rápidamente.

Los artículos sobre vulnerabilidades también incluyen una puntuación de prioridad de TI de Defender y un indicador de gravedad. La puntuación de prioridad de TI de Defender es un algoritmo único que refleja la prioridad de un CVE en función de la puntuación de CVSS, las vulnerabilidades de seguridad, las charlas y la vinculación al malware. Además, la Puntuación de prioridad de TI de Defender evalúa la recencia de estos componentes para que los usuarios puedan comprender qué CVE se deben corregir primero.

## <a name="reputation-scoring"></a>Puntuación de reputación

Defender TI proporciona puntuaciones de reputación propias para cualquier host, dominio o dirección IP. Tanto si se valida la reputación de una entidad conocida como desconocida, esta puntuación ayuda a los usuarios a comprender rápidamente los vínculos detectados con una infraestructura malintencionada o sospechosa. La plataforma proporciona información rápida sobre la actividad de estas entidades, como marcas de tiempo first y last seen, ASN, país, infraestructura asociada y una lista de reglas que afectan a la puntuación de reputación cuando corresponda.

![Tarjeta de resumen de reputación](media/reputationSummaryCard.png)

Los datos de reputación de IP son importantes para comprender la confiabilidad de su propia superficie expuesta a ataques y también es útil al evaluar hosts, dominios o direcciones IP desconocidos que aparecen en las investigaciones. Estas puntuaciones revelarán cualquier actividad malintencionada o sospechosa anterior que afectara a la entidad u otros indicadores conocidos de riesgo que se deben tener en cuenta.

Para obtener más información, consulte [Puntuación de reputación](reputation-scoring.md).

## <a name="analyst-insights"></a>Conclusiones de analistas

Las conclusiones de los analistas destilan el vasto conjunto de datos de Microsoft en una serie de observaciones que simplifican la investigación y hacen que sea más accesible para los analistas de todos los niveles.

La información está pensada para ser pequeños hechos o observaciones sobre un dominio o una dirección IP y proporcionar a los usuarios de Ti de Defender la capacidad de realizar una evaluación sobre el artefacto consultado y mejorar la capacidad de un usuario para determinar si un indicador que se está investigando es malintencionado, sospechoso o benigno.

Para obtener más información, consulte [Conclusiones de analistas](analyst-insights.md).

![Conclusiones de analistas de pestaña de resumen](media/summaryTabAnalystInsights.png)

## <a name="data-sets"></a>Conjuntos de datos
Microsoft centraliza numerosos conjuntos de datos en una única plataforma, Defender TI, lo que facilita a la comunidad de Microsoft y a los clientes realizar análisis de infraestructura. El objetivo principal de Microsoft es proporcionar tantos datos como sea posible sobre la infraestructura de Internet para admitir una variedad de casos de uso de seguridad.

Microsoft recopila, analiza e indexa datos de Internet para ayudar a los usuarios a detectar y responder a amenazas, priorizar incidentes e identificar proactivamente la infraestructura de adversarios asociada a grupos de actores que tienen como destino su organización. Microsoft recopila datos de Internet a través de la red del sensor PDNS, la red de proxy global de usuarios virtuales, los exámenes de puertos y aprovecha los orígenes de terceros para el malware y los datos del sistema de nombres de dominio (DNS) agregados.

Estos datos de Internet se clasifican en dos grupos distintos: tradicional y avanzado. Los conjuntos de datos tradicionales incluyen resoluciones, WHOIS, certificados SSL, subdominios, hashes, DNS, DNS inverso y servicios. Los conjuntos de datos avanzados incluyen rastreadores, componentes, pares de host y cookies. Los conjuntos de datos Trackers, Components, Host Pairs y Cookies se recopilan de la observación del modelo de objetos de documento (DOM) de las páginas web rastreadas. Además, también se observan componentes y rastreadores de las reglas de detección que se desencadenan en función de las respuestas de banner de los exámenes de puertos o los detalles del certificado SSL. Muchos de estos conjuntos de datos tienen varios métodos para ordenar, filtrar y descargar datos, lo que facilita el acceso a la información que puede estar asociada a un tipo de artefacto específico o a un tiempo en el historial.

Para más información, vea:

- [Ordenación, filtrado y descarga de datos](sorting-filtering-and-downloading-data.md)
- [Conjuntos de datos](data-sets.md)

![conjuntos de datos de información general de ti](media/tiOverviewDataSets.png)

## <a name="tags"></a>Etiquetas

Las etiquetas de TI de Defender se usan para proporcionar información rápida sobre un artefacto, ya sea derivado por el sistema o generado por otros usuarios. Las etiquetas ayudan a los analistas a conectar los puntos entre incidentes e investigaciones actuales y su contexto histórico para mejorar el análisis.

La plataforma de TI de Defender ofrece dos tipos de etiquetas: etiquetas del sistema y etiquetas personalizadas.

Para obtener más información, consulte [Uso de etiquetas](using-tags.md).

![Etiquetas personalizadas](media/tagsCustom.png)

## <a name="projects"></a>Projects

La plataforma de TI de Defender de Microsoft permite a los usuarios desarrollar varios tipos de proyecto para organizar indicadores de interés e indicadores de riesgo a partir de una investigación. Los proyectos contienen una lista de todos los artefactos asociados y un historial detallado que conserva los nombres, descripciones y colaboradores.

Cuando un usuario busca una dirección IP, un dominio o un host en Ti de Defender, si ese indicador aparece dentro de un proyecto al que el usuario tiene acceso, el usuario puede ver un vínculo al proyecto desde las secciones Proyectos de la pestaña Resumen, así como la pestaña Datos. Desde aquí, el usuario puede navegar hasta los detalles del proyecto para obtener más contexto sobre el indicador antes de revisar los demás conjuntos de datos para obtener más información. Esto ayuda a los analistas a evitar reinventar la rueda de una investigación que uno de sus usuarios de inquilinos de Ti de Defender puede haber iniciado o agregar a esa investigación agregando nuevos artefactos (indicadores de riesgo) relacionados con ese proyecto (si se han agregado como colaboradores al proyecto).

Para obtener más información, consulte [Uso de proyectos](using-projects.md).

![Proyectos de información general de TI de Defender](media/defenderTIOverviewProjects.png)

## <a name="data-residency-availability-and-privacy"></a>Residencia de datos, disponibilidad y privacidad

Inteligencia contra amenazas de Microsoft Defender contiene datos globales y datos específicos del cliente. Los datos subyacentes de Internet son datos globales de Microsoft; las etiquetas aplicadas por los clientes se consideran datos de clientes. Todos los datos del cliente se almacenan en la región que elija el cliente.

Por motivos de seguridad, Microsoft recopila las direcciones IP de los usuarios cuando inician sesión. Estos datos se almacenan durante un máximo de 30 días, pero pueden almacenarse más tiempo si es necesario para investigar el posible uso fraudulento o malintencionado del producto.

En el caso de un escenario de bajada de región, los clientes no deben ver ningún tiempo de inactividad, ya que TI de Defender usa tecnologías que replican datos en regiones de copia de seguridad.

Ti de Defender procesa los datos del cliente. De forma predeterminada, los datos del cliente se replican en la región emparejada.

## <a name="next-steps"></a>Siguientes pasos

Para más información, vea:

- [Inicio rápido: Obtenga información sobre cómo acceder a Inteligencia contra amenazas de Microsoft Defender y realizar personalizaciones en el portal.](learn-how-to-access-microsoft-defender-threat-intelligence-and-make-customizations-in-your-portal.md)
- [Conjuntos de datos](data-sets.md)
- [Búsqueda y dinamización](searching-and-pivoting.md)
- [Ordenación, filtrado y descarga de datos](sorting-filtering-and-downloading-data.md)
- [Encadenamiento de infraestructura](infrastructure-chaining.md)
- [Puntuación de reputación](reputation-scoring.md)
- [Conclusiones de analistas](analyst-insights.md)
- [Uso de proyectos](using-projects.md)
- [Uso de etiquetas](using-tags.md)