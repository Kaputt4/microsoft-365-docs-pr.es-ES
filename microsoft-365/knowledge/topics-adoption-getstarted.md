---
title: Empezar a impulsar la adopción de experiencias en temas (versión preliminar)
description: Obtenga información sobre cómo impulsar la adopción de experiencias de temas en su organización.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 45469e17870a58966a42a13116b6ba645071722c
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698536"
---
# <a name="get-started-driving-adoption-of-topic-experiences-preview"></a>Empezar a impulsar la adopción de experiencias en temas (versión preliminar)

> [!Note]
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).

Antes de empezar con la adopción, debe comprender los conceptos relacionados con la administración de conocimientos y las experiencias de los temas. El siguiente diagrama muestra lo que sucede durante la detección de temas y curation:

![Tema de la arquitectura de experiencias](../media/knowledge-management/topic-management-architecture.png)

- **Detección**: los usuarios pueden descubrir los conocimientos en las aplicaciones que usan todos los días a través de las tarjetas de temas: también pueden descubrir temas en Microsoft Search.
- **Curation**: los expertos en la materia (SME) refinan los temas a través de las páginas del tema y los elementos AI aprenderán de su entrada. El centro de temas contiene páginas de temas que los usuarios pueden explorar y que los expertos pueden administrar.
- **Identificación**: con Microsoft Graph y el conocimiento y las personas de inteligencia artificial (AI) se identifican y organizan automáticamente en temas relacionados. El contenido de SharePoint se indiza con contenido de seguridad.
- **Extensión**: con los conectores de contenido de Microsoft Graph (próximamente), puede ingestar el conocimiento de los servicios externos y de los repositorios de datos.

Para obtener más información, puede revisar la [información general](topic-experiences-overview.md) de una introducción.

Tenga en cuenta que:

- El descubrimiento de temas se ha mejorado cuando hay más contenido disponible.
- La seguridad, la privacidad y la ubicación de los datos se conservan aunque la información se presente en una nueva experiencia.
- Los usuarios necesitan una licencia para ver las experiencias de los temas.
- La detección se encuentra inicialmente en el contenido del idioma inglés.

Para ayudarle a prepararse, piense en estas preguntas:

- ¿Qué contenido debe usarse para la detección de temas?
- ¿Quién va a administrar los temas?
- ¿Quién verá las tarjetas de temas y los puntos destacados?
- ¿Qué temas se esperan?

Revise esta lista de requisitos previos para sacar el máximo partido a las experiencias de tema:

|Producto o característica |Descripción |
|:-------|:--------|
|SharePoint Online con páginas modernas de SharePoint |La minería de temas solo incluye contenido en los sitios de SharePoint, y las tarjetas de tema solo se pueden exponer en las páginas modernas.|
|Microsoft Graph |Puede controlar si los temas se incluyen o excluyen de la búsqueda o ahondar en la configuración de Microsoft Graph. |

## <a name="plan-for-adoption"></a>Planeación de la adopción

Para planear la adopción de experiencias en un tema, debe:

![Pasos para planear la adopción](../media/knowledge-management/km-adoption-plan-adoption.png)

1. Planee el enfoque y los escenarios de destino:
    - Piense en definir y establecer prioridades en los [escenarios](#target-scenarios).
    - Piense en las [partes interesadas](#identify-stakeholders) y los miembros del equipo del proyecto que necesita que participen.  
    - Calcule Qué impacto empresarial desea impulsar y cómo va a [medir el éxito](#create-a-success-plan).

2. Participe en su organización:
    - Identifique los grupos de negocio y los equipos de negocio que deben estar involucrados y obtenga una alineación con respecto a los escenarios que está planeando.
    - Comience a pensar sobre cómo participar en los primeros implantadores para obtener comentarios críticos y anticipados para que pueda iterar para obtener la mejor solución.
    - Empiece a crear la comunidad y piense cómo pueden usarse las experiencias de tema en toda la organización mediante estos grupos diferentes.

3. Entrenar a su organización: la mayoría de las personas comprenderán de forma intuitiva el concepto de temas y la forma en que las tarjetas de temas compilan la información relevante y comprenderán y verán el valor. Pero es posible que desee crear un entrenamiento adaptado a su cultura y organización, para mostrar cómo desea que se usen las experiencias de los temas en su organización. Algunos recursos de aprendizaje:
    - [Centro de recursos de Project Cortex](https://aka.ms/projectcortex). Incluye información general e información sobre las características, presentaciones y vídeos de Office hour grabados, e información sobre socios y sus ofertas.
    - Próximamente, vídeos de formación y ayuda para usuarios finales.

4. [Cree una red de experto](#build-a-champion-network):
    - Es posible que tenga comunidades de prácticas o redes de expertos que ya estén en su ubicación. Estas son excelentes formas de sociales y promocionar y de obtener colegas involucrados en ayuda mutua. Y pueden compartir historias de éxito que pueden ser realmente valiosas. Pueden ofrecer consejos y generar entusiasmo.

### <a name="target-scenarios"></a>Escenarios de destino

El por qué ayuda a determinar qué modelo será necesario y cómo estructurar la organización en función del lugar en el que se aplicará el modelo. Estos son algunos escenarios donde la administración de la información puede ayudar a su organización:

- Aprendizaje de la incorporación de roles &: comprender la terminología, los proyectos clave y la cultura de una nueva organización son pasos importantes para la incorporación. Un sencillo descubrimiento de temas puede ayudar a los nuevos empleados a ponerse al día en nuevos trabajos, roles o proyectos de forma rápida.
- Experiencia de búsqueda y uso compartido de información: cuando los temas se administran y se comparten, las personas de sus organizaciones pueden encontrar más fácilmente información y expertos para ayudarles en su trabajo cotidiano.
- La toma de decisiones ampliada y el tiempo de comercialización mejorado: cuando la información y los expertos son fáciles de alcanzar, puede tomar decisiones más fácilmente y ahorrar proyectos de tiempo libre.

Por ejemplo, aquí se muestra un escenario para la incorporación de roles:

- Un empleado (Jordania) está tomando un nuevo rol o se ha contratado recientemente y solo empieza con un rol. Jordania quiere estar involucrado y ser productivo tan rápido como sea posible. Pero Jordania también necesita ayuda para encontrar un punto de partida.
- Un colega (Kim) que estaba en la función antes de que el Jordania creó páginas de temas que pueden ayudarle a nuevos empleados y a otras personas que busquen esa información.
- Kim era una SME y tenía permisos para mirar en páginas de temas no confirmados. Las páginas de temas no confirmadas son excelentes puntos de inicio para lo que los complementos de AI han descubierto y creado, y Kim ha podido modificarlas para agregar recursos de experto, definiciones y otros recursos.
- A medida que Jordania Lee una nueva publicación de SharePoint, Jordania ve un resaltado de tema y se desplaza sobre él para obtener rápidamente una definición del término y con quién ponerse en contacto con más preguntas. Antes, es posible que Jordania haya tenido que buscar esta información y ponerse en contacto con los colegas para ver a quién hacer algo.
- La exposición de esta información a través de las experiencias de los temas puede ser muy eficaz, ya que aunque esta información puede haber estado disponible antes, es posible que haya sido siloda y difícil de encontrar. Gracias a las aplicaciones que usa Jordania y ayuda a Jordania, estos expertos también pueden impulsar una sensación de participación y de la comunidad. También puede ayudar a que el Jordania se sienta más capacitado al tratar con el nuevo rol.

Después de identificar los escenarios, puede priorizar los escenarios:

Una forma de establecer prioridades es trazar los escenarios en una cuadrícula que muestre el impacto y la facilidad de implementación. Busque escenarios que tengan un gran impacto y sean fáciles de implementar. Convierta esos en su primera prioridad. Los escenarios de bajo impacto y de difícil implementación son la prioridad más baja. Cuando tiene una victoria rápida con un gran impacto y un escenario de fácil implementación, ayuda a los usuarios a estar entusiasmados y ver las posibilidades de usar los temas.

![Gran impacto, escenarios fáciles de implementar son de alta prioridad](../media/knowledge-management/topics-prioritize-scenarios.png)

Elija un par de escenarios clave para centrarse en principio, trabajar con los primeros que han adoptado para obtener comentarios y, a continuación, implementar en fases. De esta forma, podrá iterar, realizar mejoras y obtener comentarios para que pueda aumentar la adopción a lo largo del tiempo. 

### <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Identifique a las partes interesadas del proyecto. Las funciones clave son el Patrocinador Ejecutivo, el propietario del éxito y los expertos.

|Role |Responsibilities |Department |
|:-------|:-------|:--------|
| Patrocinadores ejecutivos   | Comunicar la visión y los valores de alto nivel a la empresa   |  Liderazgo ejecutivo   |
| Jefes de proyecto | Supervisar todo el proceso de ejecución e implementación de inicio | Administración de proyectos |
| Administradores de conocimiento| Instalar y configurar experiencias de temas | Departamento de ti |
| Administradores de conocimiento | Administrar temas y supervisar la taxonomía | Cualquier departamento |
| Administradores de taxonomía | Supervisar la taxonomía | Cualquier departamento |
| Colaboradores y contribuyentes de temas en materia de expertos | Generar o revisar temas y descripciones | Cualquier departamento |
| Expertos: | Ayudar a repartir y administrar el manejo de objeciones | Cualquier departamento (personal) |
| Administrador de inquilinos | Configurar la configuración de nivel de inquilino | Departamento de ti |
| Administrador de plataforma de energía| Configuración del entorno de servicios de datos comunes | Departamento de ti |
| Administrador o administrador de búsqueda | Configuración de las opciones de búsqueda | Departamento de ti |

En una organización de mayor tamaño, es posible que también tenga varias personas en estas funciones y necesitará impulsar la coordinación entre ellos. En una compañía más pequeña, es posible que una sola persona realice varias de estas funciones. Diferentes funciones del proyecto podrían ser más complicadas en distintas fases. Por ejemplo, algunas personas están más involucradas en la configuración de las características de (administradores de inquilinos), mientras que otras no se ven afectadas hasta que se empieza a definir que los temas están más involucrados en el mantenimiento (expertos en el tema y los expertos).
 
Aunque le recomendamos que cada una de estas funciones se cumplan a lo largo de su distribución, es posible que no se requiera todo para empezar a trabajar con la solución identificada.

### <a name="create-a-success-plan"></a>Crear un plan de éxito

Use estos indicadores para medir el éxito de las experiencias de los temas de la organización. Mira:

1. Uso del tema:
      - Impresiones de temas
      - Cantidad de temas: confirmados y no confirmados en la lista de temas de creados.
      - Número de páginas de temas publicadas.
1. Comentarios de los usuarios finales de las tarjetas de temas.
1. Realizar encuestas de satisfacción de los empleados. Los temas deben mejorar la capacidad de los empleados para encontrar información, de modo que encuentre formas de recopilar sus comentarios y comentarios sobre ello.
1. Impacto positivo en el análisis de búsqueda. Como los temas aparecen en la experiencia de búsqueda, con el tiempo puede ver tasas más bajas de búsquedas abandonadas, ya que los usuarios pueden encontrar fácilmente los temas en la búsqueda. 

### <a name="build-a-champion-network"></a>Crear una red de experto

Cree una red de experto en su organización. Los expertos son importantes porque pueden:

- Crear un círculo de influencia entre sus equipos
- Administración de temas de la administración & mantenimiento

Puede contratar a los expertos de diferentes roles: administradores de conocimiento y expertos en el tema.

Muchos de los defensores de las redes aprovechan Yammer como plataforma. En Yammer, los usuarios pueden publicar preguntas y obtener respuestas y compartir historias de éxito. Es difícil extraer la palabra solo, de modo que puede confiar en la red de las personas de su empresa para ofrecer consejo a sus colegas y mostrar cómo el equipo está usando experiencias de temas para que otros equipos puedan pensar en sus propios escenarios.

Algunas organizaciones usan hackathons (formal o informal, virtual o en persona) para recopilar grupos de personas para trabajar en un proyecto específico. Por ejemplo, podría recopilar a sus expertos en el tema y hacer que trabajen juntos para Curate un conjunto de páginas de temas.

Piense en cómo puede reconocer a sus expertos. Recompensan sus actividades, les proporcionan algún reconocimiento y generan una sensación y una contratación de la comunidad visible para que se sientan como que contribuyen a algo y también están recibiendo algo de ti.

Ahora que ya está listo para implementarlo, desea asegurarse de que está fomentando la contratación en curso.

- Mantenga los grupos de Yammer activos para sus expertos.
- Compartir historias de éxitos.
- Hospede periódicamente eventos adicionales para compartir artículos o introducir nuevas características.
- Establecer desafíos para las personas y ejecutar convocatorias.

## <a name="next-steps"></a>Siguientes pasos

Cuando esté listo para implementar las experiencias de los temas, necesitará obtener personas involucradas.

- Comience a introducir el conjunto de características y a obtenerlos para pensar en sus escenarios.
- Reúna a las partes interesadas y cree escenarios.
- Lleve la comunidad y piense cómo va a activarla.
- A continuación, complete los pasos de preparación. Algunas pueden ser de preparación técnica y de cierta disponibilidad empresarial.
- Por último, social y Promote.
