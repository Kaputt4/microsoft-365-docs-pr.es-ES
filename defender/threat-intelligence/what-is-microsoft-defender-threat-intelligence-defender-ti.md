---
title: ¿Qué es Inteligencia sobre amenazas de Microsoft Defender (Defender TI)?
description: En este artículo de información general, obtendrá información sobre las características principales que se incluyen con inteligencia sobre amenazas de Microsoft Defender (TI de Defender).
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: overview
ms.date: 08/02/2022
ms.custom: template-overview
ms.openlocfilehash: 62e3df65479bec45896504dc8eda006e2a41d75b
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67739276"
---
# <a name="what-is-microsoft-defender-threat-intelligence-defender-ti"></a>¿Qué es Inteligencia sobre amenazas de Microsoft Defender (Defender TI)?

La inteligencia sobre amenazas de Microsoft Defender (Defender TI) es una plataforma que simplifica la evaluación de prioridades, la respuesta a incidentes, la búsqueda de amenazas, la administración de vulnerabilidades y los flujos de trabajo de analistas de inteligencia sobre ciberamenazas al realizar análisis de la infraestructura de amenazas y recopilar inteligencia sobre amenazas. Los analistas dedican una gran cantidad de tiempo a la detección, recopilación y análisis de datos, en lugar de centrarse en lo que realmente ayuda a su organización a defenderse, derivando información sobre los actores a través del análisis y la correlación.

En muchas ocasiones, los analistas deben ir a varios repositorios para obtener los conjuntos de datos críticos que necesitan para evaluar un dominio, host o dirección IP sospechosos. Los datos DNS, la información WHOIS, el malware y los certificados SSL proporcionan un contexto importante a los indicadores de riesgo (IOC), pero estos repositorios están ampliamente distribuidos y no siempre comparten una estructura de datos común, lo cual ha hecho difícil que los analistas tengan todos los datos pertinentes necesarios para realizar una evaluación adecuada y oportuna de la infraestructura sospechosa.

Interactuar con estos conjuntos de datos puede ser complicado y dinamizar entre estos repositorios requiere mucho tiempo, lo que consume recursos de grupos de operaciones de seguridad que necesitan volver a priorizar constantemente sus esfuerzos de respuesta.

Los analistas de inteligencia sobre ciberamenazas han tenido dificultades para equilibrar una amplitud de la ingesta de inteligencia sobre amenazas con el análisis de qué inteligencia sobre amenazas supone las amenazas más importantes para su organización o sector.

En la misma amplitud, los analistas de inteligencia de vulnerabilidades luchan por correlacionar su inventario de recursos con la información de CVE para priorizar la investigación y la corrección de las vulnerabilidades más críticas asociadas a su organización.

El objetivo de Microsoft es volver a imaginar el flujo de trabajo del analista mediante el desarrollo de una plataforma, TI de Defender, que agrega y enriquece orígenes de datos críticos y muestra los datos en una interfaz innovadora y fácil de usar para correlacionar cuándo los indicadores están vinculados a artículos y vulnerabilidades, la cadena de infraestructura junto con indicadores de compromiso (IOC) y colaborar en investigaciones con otros usuarios con licencia de TI de Defender dentro de su inquilino. Con las organizaciones de seguridad que actúan una cantidad cada vez mayor de inteligencia y alertas dentro de su entorno, con un análisis de amenazas y La plataforma de inteligencia que permite evaluaciones precisas y oportunas de las alertas resulta importante.

A continuación se muestra una recorte de pantalla de la página principal de inteligencia sobre amenazas de TI de Defender. Los analistas pueden examinar rápidamente nuevos artículos destacados, así como iniciar sus esfuerzos de recopilación, evaluación de prioridades, respuesta a incidentes y búsqueda de inteligencia mediante la realización de una búsqueda de palabra clave, artefacto o CVE-ID.

![Recorte de pantalla de Información general de TI de Edge](media/tiOverviewEdgeScreenshot.png)

## <a name="defender-ti-articles"></a>Artículos de TI de Defender
Los artículos son narraciones de Microsoft que proporcionan información sobre actores de amenazas, herramientas, ataques y vulnerabilidades. Los artículos y destacados de TI de Defender no son entradas de blog sobre inteligencia sobre amenazas; aunque resumen las distintas amenazas, también se vinculan a contenido accionable e indicadores clave de compromiso para ayudar a los usuarios a tomar medidas. Al incluir esta información técnica en los resúmenes de amenazas, se permite a los usuarios realizar un seguimiento continuo de los actores de amenazas, las herramientas, los ataques y las vulnerabilidades a medida que cambian.

## <a name="featured-articles"></a>Artículos destacados

En la sección de artículos destacados de la página principal de inteligencia sobre amenazas de TI de Defender (justo debajo de la barra de búsqueda) se muestra el contenido destacado de Microsoft:

![Artículos destacados de información general de TI](media/tiOverviewFeaturedArticles.png)

Al hacer clic en el artículo, se le lleva al contenido del artículo subyacente. La sinopsis del artículo proporciona al usuario una descripción rápida del artículo. La llamada Indicadores muestra cuántos indicadores de TI públicos y de Defender están asociados al artículo.

![Artículo destacado de información general de TI](media/tiOverviewFeaturedArticle.png)

## <a name="articles"></a>Artículos

Todos los artículos (incluidos los artículos destacados) se enumeran en la sección de artículos de la página principal de inteligencia sobre amenazas de TI de Microsoft Defender, ordenados por fecha de creación (descendente):

![Artículos de información general de TI](media/tiOverviewArticles.png)

## <a name="article-descriptions"></a>Descripciones de artículos

La sección de descripción de la pantalla de detalles del artículo contiene información sobre el ataque o el atacante del que se ha generado el perfil. El contenido puede oscilar entre muy corto (en el caso de los boletines OSINT) o bastante largo (para los informes de formato largo, especialmente cuando Microsoft ha aumentado el informe con contenido). Las descripciones más largas pueden contener imágenes, vínculos al contenido subyacente, vínculos a búsquedas en TI de Defender, fragmentos de código de atacante y reglas de firewall para bloquear el ataque:

![Descripción del artículo de información general de TI](media/tiOverviewArticleDescription.png)

## <a name="public-indicators"></a>Indicadores públicos

En la sección de indicadores públicos de la pantalla se muestran los indicadores publicados anteriormente relacionados con el artículo. Los vínculos de los indicadores públicos llevan uno a los datos de TI de Defender subyacentes o a los orígenes externos pertinentes.

![Indicadores públicos de artículos de información general de TI](media/tiOverviewArticlePublicIndicators.png)

## <a name="defender-ti-indicators"></a>Indicadores de TI de Defender

La sección de indicadores de TI de Defender cubre los indicadores que el equipo de investigación de TI de Defender ha encontrado y agregado a los artículos.

Estos vínculos también se dividen en los datos relevantes de TI de Defender o en el origen externo correspondiente.

![Información general de TI Indicadores de TI de Defender](media/tiOverviewArticleDefenderTiIndicators.png)

## <a name="vulnerability-articles"></a>Artículos sobre vulnerabilidades

TI de Defender ofrece búsquedas CVE-ID para ayudar a los usuarios a identificar información crítica sobre CVE. Las búsquedas de CVE-ID dan como resultado artículos de vulnerabilidad.

Los artículos de vulnerabilidad proporcionan un contexto clave detrás de los CVE de interés. Cada artículo contiene una descripción de CVE, una lista de componentes afectados, procedimientos y estrategias de mitigación adaptados, artículos de inteligencia relacionados, referencias en profundidad y La web oscura y otras observaciones clave. Estos artículos proporcionan un contexto más profundo y conclusiones útiles detrás de cada CVE, lo que permite a los usuarios comprender más rápidamente estas vulnerabilidades y mitigarlas rápidamente.

Los artículos de vulnerabilidad también incluyen una puntuación de prioridad de TI de Defender y un indicador de gravedad. La puntuación de prioridad de TI de Defender es un algoritmo único que refleja la prioridad de un CVE en función de la puntuación de CVSS, las vulnerabilidades de seguridad, la charla y la vinculación con malware. Además, la puntuación de prioridad de TI de Defender evalúa la capacidad de estos componentes para que los usuarios puedan comprender qué CVE deben corregirse primero.

## <a name="reputation-scoring"></a>Puntuación de reputación

TI de Defender proporciona puntuaciones de reputación de propiedad para cualquier host, dominio o dirección IP. Si se valida la reputación de una entidad conocida o desconocida, esta puntuación ayuda a los usuarios a comprender rápidamente los vínculos detectados a una infraestructura malintencionada o sospechosa. La plataforma proporciona información rápida sobre la actividad de estas entidades, como las marcas de tiempo De primera y Última vista, ASN, país, infraestructura asociada y una lista de reglas que afectan a la puntuación de reputación cuando corresponda.

![Tarjeta de resumen de reputación](media/reputationSummaryCard.png)

Los datos de reputación de IP son importantes para comprender la confiabilidad de su propia superficie expuesta a ataques y también son útiles para evaluar hosts, dominios o direcciones IP desconocidos que aparecen en las investigaciones. Estas puntuaciones descubrirán cualquier actividad malintencionada o sospechosa anterior que afecte a la entidad, u otros indicadores conocidos de riesgo que se deben tener en cuenta.

Para obtener más información, consulte [Puntuación de reputación](reputation-scoring.md).

## <a name="analyst-insights"></a>Conclusiones de analistas

Las conclusiones de los analistas convierten el amplio conjunto de datos de Microsoft en una serie de observaciones que simplifican la investigación y hacen que sea más accesible para los analistas de todos los niveles.

Las informaciones están pensadas para ser pequeños hechos u observaciones sobre un dominio o dirección IP y proporcionan a los usuarios de Defender TI la capacidad de realizar una evaluación sobre el artefacto consultado y mejorar la capacidad del usuario para determinar si el indicador que se está investigando es malicioso, sospechoso o benigno.

Para obtener más información, consulte [Información del analista](analyst-insights.md).

![Información del analista de la pestaña Resumen](media/summaryTabAnalystInsights.png)

## <a name="data-sets"></a>Conjuntos de datos
Microsoft centraliza numerosos conjuntos de datos en una sola plataforma, DEFENDER TI, lo que facilita a la comunidad de Microsoft y a los clientes la realización de análisis de la infraestructura. El objetivo principal de Microsoft es proporcionar tantos datos como sea posible sobre la infraestructura de Internet para admitir una variedad de casos de uso de seguridad.

Microsoft recopila, analiza e indexa datos de Internet para ayudar a los usuarios a detectar amenazas y responder a ellas, priorizar incidentes e identificar proactivamente a los adversarios. infraestructura asociada a grupos de actores que tienen como destino su organización. Microsoft recopila datos de Internet a través de su Red de sensores PDNS, red de proxy global de usuarios virtuales, exámenes de puertos y aprovecha orígenes de terceros para malware y datos agregados del Sistema de nombres de dominio (DNS).

Estos datos de Internet se clasifican en dos grupos distintos: tradicional y avanzado. Los conjuntos de datos tradicionales incluyen resoluciones, WHOIS, certificados SSL, subdominios, DNS, DNS inverso y servicios. Los conjuntos de datos avanzados incluyen rastreadores, componentes, pares de hosts y cookies. Los conjuntos de datos rastreadores, componentes, pares host y cookies se recopilan al observar el Document Object Model (DOM) de las páginas web rastreadas. Además, los componentes y rastreadores también se observan a partir de reglas de detección que se desencadenan en función de las respuestas de banner de los exámenes de puerto o los detalles del certificado SSL. Muchos de estos conjuntos de datos tienen varios métodos para ordenar, filtrar y descargar datos, lo que facilita el acceso a información que puede estar asociada a un tipo de artefacto específico o a una hora en el historial.

Para más información, vea:

- [Ordenar, filtrar y descargar datos](sorting-filtering-and-downloading-data.md)
- [Conjuntos de datos](data-sets.md)

![conjuntos de datos de información general de TI](media/tiOverviewDataSets.png)

## <a name="tags"></a>Etiquetas

Las etiquetas ti de Defender se usan para proporcionar información rápida sobre un artefacto, ya sea derivado por el sistema o generado por otros usuarios. Las etiquetas ayudan a los analistas a conectar los puntos entre los incidentes e investigaciones actuales y su contexto histórico para mejorar el análisis.

La plataforma TI de Defender ofrece dos tipos de etiquetas: etiquetas del sistema y etiquetas personalizadas.

Para obtener más información, consulte [Usar etiquetas](using-tags.md).

![Etiquetas personalizadas](media/tagsCustom.png)

## <a name="projects"></a>Projects

La plataforma DE TI de Microsoft Defender permite a los usuarios desarrollar varios tipos de proyectos para organizar indicadores de interés e indicadores de compromiso de una investigación. Los proyectos contienen una lista de todos los artefactos asociados y un historial detallado que conserva los nombres, las descripciones y los colaboradores.

Cuando un usuario busca una dirección IP, un dominio o un host en Defender TI, si ese indicador aparece en un proyecto al que el usuario tiene acceso, el usuario puede ver un vínculo al proyecto desde las secciones Proyectos de la pestaña Resumen, así como desde la pestaña Datos. Desde aquí, el usuario puede navegar a los detalles del proyecto para obtener más contexto sobre el indicador antes de revisar los demás conjuntos de datos para obtener más información. Esto ayuda a los analistas a evitar reinventar la rueda de una investigación que uno de sus usuarios inquilinos de Defender TI puede haber iniciado o agregar a esa investigación agregando nuevos artefactos (indicadores de compromiso) relacionados con ese proyecto (si se han agregado como colaboradores al proyecto).

Para obtener más información, consulte [Usar proyectos](using-projects.md).

![Proyectos de información general de Defender TI ](media/defenderTIOverviewProjects.png)

## <a name="data-residency-availability-and-privacy"></a>Residencia, disponibilidad y privacidad de los datos

La inteligencia sobre amenazas de Microsoft Defender contiene datos globales y datos específicos del cliente. Los datos subyacentes de Internet son datos globales de Microsoft; las etiquetas aplicadas por los clientes son consideradas datos de clientes. Todos los datos del cliente se almacenan en la región que elija el cliente.

Por motivos de seguridad, Microsoft recopila las direcciones IP de los usuarios cuando inician sesión. Estos datos se almacenan durante un máximo de 30 días, pero pueden almacenarse más tiempo si es necesario para investigar el posible uso fraudulento o malintencionado del producto.

En el caso de un escenario de región inactiva, los clientes no deberían ver ningún tiempo de inactividad, ya que Defender TI usa tecnologías que replican datos en regiones de copia de seguridad.

TI de Defender procesa los datos de los clientes. De forma predeterminada, los datos del cliente se replican en la región emparejada.

## <a name="next-steps"></a>Siguientes pasos

Para más información, vea:

- [Guía de inicio rápido: Obtenga información sobre cómo acceder a la inteligencia sobre amenazas de Microsoft Defender y realizar personalizaciones en el portal](learn-how-to-access-microsoft-defender-threat-intelligence-and-make-customizations-in-your-portal.md)
- [Conjuntos de datos](data-sets.md)
- [Búsqueda y dinamización](searching-and-pivoting.md)
- [Ordenar, filtrar y descargar datos](sorting-filtering-and-downloading-data.md)
- [Encadenamiento de infraestructura](infrastructure-chaining.md)
- [Puntuación de reputación](reputation-scoring.md)
- [Conclusiones de analistas](analyst-insights.md)
- [Uso de proyectos](using-projects.md)
- [Uso de etiquetas](using-tags.md)
