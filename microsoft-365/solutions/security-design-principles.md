---
title: 'Planeación de recursos de Microsoft 365 Enterprise: arquitectura de ciberseguridad'
description: Obtenga información sobre cómo superar los desafíos de seguridad en la arquitectura de Microsoft Enterprise desde Lareta Ala, arquitecto de ciberseguridad de Microsoft.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 7b84094fecc1ddbd58bcdfca808df6585958a6dc
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771936"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Obstáculos de seguridad que puede superar: el punto de vista de un arquitecto

En este [artículo,EttetaEtt,](https://www.linkedin.com/in/kozeta-garrett-53013a6/)cybersecurity architect de Microsoft, describe los principales desafíos de seguridad que se encuentran en las organizaciones empresariales y recomienda enfoques para navegar por estos obstáculos.

## <a name="about-the-author"></a>Acerca del autor

![Foto de Resepareta Desmonta](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

En mi rol de arquitecto de seguridad en la nube, he trabajado con varias organizaciones para proporcionar instrucciones técnicas y estratégicas centradas en diseñar e implementar la arquitectura de seguridad para los clientes que migran a Microsoft 365 y Azure, desarrollan soluciones de seguridad empresariales y ayudan a transformar la arquitectura y la cultura de seguridad para la resistencia empresarial. Mi experiencia incluye la detección y respuesta de incidentes, el análisis de malware, las pruebas de penetración y la recomendación de mejoras en la seguridad y la posición de defensa de IT. Me encantan las transformaciones iniciales que resultan en la seguridad como un habilitador para la empresa, incluidos los esfuerzos de modernización.

Ha sido muy satisfactorio ver cómo las organizaciones que adoptaron una idea de modernización de seguridad en los últimos dos años se encuentran en una posición excelente que les permite seguir funcionando de forma remota de forma segura, a pesar de la reciente situación de covid-19. Desafortunadamente, estas circunstancias también han funcionado como una llamada de activación para algunos clientes, que no estaban preparados para esta necesidad inmediata. Muchas organizaciones se están dando cuenta de que deben modernizarse rápidamente, retirar la deuda de seguridad de TI acumulada y mejorar su posición de seguridad durante la noche para que puedan operar en estas circunstancias extremadamente inusuales.

La buena noticia es que Microsoft ha seleccionado algunos recursos excelentes para ayudar a las organizaciones a aumentar rápidamente su posición de seguridad. Además de estos recursos, me gustaría compartir los principales desafíos que he encontrado con los clientes a diario con la expectativa de que pueda navegar por estos obstáculos.

Actualmente vivo en El Norte de Washington, cerca de la capital de nuestro país, Washington DC. Me gustan casi todas las formas de actividades y ejercicios al aire libre, como correr, andar en bicicleta, desfilando y desfilando. Para hacer frente a estos, disfrute tanto de la cocina, de la comida y de los viajes.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Asociarse con el equipo de seguridad desde el inicio de la adopción de la nube

Para empezar, no puedo enfatizar lo importante que es coordinar los equipos de su organización desde el principio. Los equipos de seguridad deben adoptarse como socios críticos en las primeras etapas de diseño y adopción de la nube. Esto significa incorporar equipos de seguridad a la adopción de la nube de expertos, no solo para las funcionalidades agregadas a la empresa (como una excelente experiencia de usuario desde dispositivos móviles seguros, aplicaciones de funcionalidad completa o creación de valor en datos corporativos más allá de las aplicaciones de productividad y correo electrónico de funcionalidad limitada), sino también para aprovechar las capacidades de almacenamiento, inteligencia artificial e informática que ayudan a resolver los nuevos y antiguos desafíos de seguridad. Los equipos de seguridad deben incluirse en la administración de todos los aspectos de este cambio, incluidas las personas (cultura), los procesos (formación) y la tecnología para que sean correctos. También implica invertir en la modernización y mejora continua del Centro de operaciones de seguridad (SOC). Trabaje juntos para alinear su estrategia de seguridad con la estrategia empresarial y las tendencias del entorno para garantizar que la transformación digital se realiza de forma segura. Cuando esto se hace bien, las organizaciones desarrollan la capacidad de adaptarse más rápido a los cambios, incluidos los cambios en la empresa, TI y seguridad.

Donde veo que los clientes se desacarra más es cuando no hay ninguna asociación real entre las operaciones y los equipos de SOC. Mientras el equipo de operaciones se presiona y exige con plazos ajustados para adoptar la nube, los equipos de seguridad no siempre se incluyen al principio del proceso para revisar y planear una estrategia de seguridad completa. Esto implica la integración de componentes y componentes de nube diferentes de forma preconfigura. Esta falta de asociación se abate aún más a diferentes equipos que parecen trabajar en silos para implementar controles para sus componentes específicos, lo que conduce a la complejidad adicional de la implementación, la solución de problemas y la integración.

Los clientes que navegan por estos obstáculos tienen buenas asociaciones entre las operaciones y el gobierno y los equipos de administración de seguridad y riesgos para renovar la estrategia de seguridad y los requisitos para proteger las cargas de trabajo en la nube híbrida. Se centran en los objetivos y los resultados de seguridad finales: la protección de datos y la disponibilidad de sistemas y servicios de acuerdo con los requisitos de cumplimiento, riesgos y gobierno de ciberseguridad. Estas organizaciones desarrollan asociaciones de fase temprana entre su equipo de operaciones y gobierno y SOC, lo que es fundamental para el enfoque de diseño de seguridad y maximizará el valor de sus inversiones.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Crear un perímetro de seguridad moderno (basado en identidades)

A continuación, adopte un enfoque de arquitectura de confianza cero. Esto comienza con la creación de un perímetro de seguridad moderno basado en identidades. Diseñe la arquitectura de seguridad donde cada intento de acceso, ya sea local o en la nube, se trate como no confiable hasta que se compruebe: "nunca confíe, compruebe siempre". Este enfoque de diseño no solo aumenta la seguridad y la productividad, sino que también permite a los usuarios trabajar desde cualquier lugar con cualquier tipo de dispositivo. Los sofisticados controles en la nube incluidos con Microsoft 365 le ayudan a proteger las identidades de los usuarios a la vez que controlan el acceso a recursos valiosos en función del nivel de riesgo del usuario.

Para obtener una configuración recomendada, consulte [Configuraciones de acceso de dispositivos e identidades.](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="transition-security-controls-to-the-cloud"></a>Controles de seguridad de transición a la nube

Muchos equipos de seguridad siguen usando los procedimientos recomendados de seguridad tradicionales creados para un mundo local, incluido el mantenimiento de una "seguridad perimetral de red" y el intento de "forzar" las herramientas y controles de seguridad locales a las soluciones en la nube. Estos controles no se diseñaron para la nube, son ineficaces y obstaculizan la adopción de funcionalidades de nube modernas. Los procesos y herramientas que funcionan para un enfoque de seguridad perimetral de red han demostrado ser ineficaces, obstaculizan las capacidades de la nube y no permiten aprovechar las características de seguridad modernas y automatizadas.

Puede superar este obstáculo cambiando las estrategias de defensa a la protección administrada por la nube, investigación y corrección automatizadas, pruebas de lápiz automatizadas, Defender para Office 365 y análisis de incidentes. Los clientes que usan soluciones modernas de administración de dispositivos han implementado la administración automatizada, revisiones estandarizadas, antivirus, aplicación de directivas y protección de aplicaciones en todos los dispositivos (ya sea un smartphone, un equipo personal, un portátil o una tableta). Esto elimina la necesidad de una VPN, Microsoft System Center Configuration Manager (SCCM) y directivas de grupo de Active Directory. Esto, combinado con las directivas de acceso condicional, proporciona un control y visibilidad eficaces, así como un acceso optimizado a los recursos independientemente de desde dónde operan sus usuarios.

## <a name="strive-for-best-together-security-tools"></a>Buscar herramientas de seguridad "mejores juntos"

Otro obstáculo que veo a los clientes es tomar un enfoque de "lo mejor posible" para las herramientas de seguridad. La distribución continua de soluciones de puntos de "mejor calidad" para satisfacer las necesidades de seguridad emergentes hace que la seguridad empresarial se rompa. Incluso con las mejores intenciones, las herramientas de la mayoría de los entornos no se integran porque se vuelve demasiado costosa y compleja. Esto, a su vez, crea diferencias en la visibilidad, ya que hay más alertas para la triage que el equipo puede controlar. Volver a entrenar al equipo de SecOps en nuevas herramientas también se convierte en un desafío constante.

El enfoque "simple es mejor" también funciona para la seguridad. En lugar de seguir las herramientas "más adecuadas", se desfila por este obstáculo adoptando una estrategia "mejor juntos" con herramientas que funcionen juntas de forma predeterminada. Las capacidades de seguridad de Microsoft protegen toda la organización con protección contra amenazas integrada que abarca aplicaciones, usuarios y nubes. La integración permite a una organización ser más resistente y reducir el riesgo al contener atacantes en la entrada y corregir rápidamente los ataques.

## <a name="balance-security-with-functionality"></a>Equilibrar la seguridad con la funcionalidad

Como soy de una experiencia y un entorno de ciberseguridad largos, tiendo a preferir empezar con la configuración más segura de forma predeterminada y permitir que las organizaciones relajen las configuraciones de seguridad en función de sus necesidades operativas y de seguridad. Sin embargo, esto puede llegar a un precio elevado por la pérdida de funcionalidad y la mala experiencia del usuario. Como muchas organizaciones han aprendido, si la seguridad es demasiado difícil para los usuarios, encontrarán una forma de evitarlo, incluido el uso de servicios en la nube no administrados. Tan difícil como para mí aceptar, he llegado a comprender que se debe lograr el equilibrio entre funcionalidad y seguridad.

Las organizaciones que se dan cuenta de que los usuarios harán lo que sea necesario para realizar su trabajo reconocen que no vale la pena enfrentarse a la "sombra de TI". Reconocen que los empleados de TI son los mayores obstáculos cuando se trata de ti en la sombra y el uso de aplicaciones SaaS no aprobadas para su trabajo. Han cambiado su estrategia para fomentar su uso (en lugar de suprimir) y centrarse en mitigar los riesgos que podría crear. Los equipos de seguridad de esta organización no insisten en que todo se bloquee, se registra y se envíe a través de un proxy inverso o una VPN. En su lugar, estos equipos de seguridad duplican sus esfuerzos para proteger los datos confidenciales y valiosos de ser expuestos a las partes o aplicaciones malintencionadas incorrectas. Funcionan para proteger la integridad de los datos. Están haciendo un uso completo de las capacidades más avanzadas de protección de la información en la nube, incluido el cifrado, la autenticación multifactor segura, el riesgo automatizado y el cumplimiento, y las capacidades de Cloud App Security Broker (CASB), a la vez que permiten e incluso fomentan el uso compartido protegido en varias plataformas. Están convirtiendo las tecnologías de la información de instantáneas en una creatividad, productividad y colaboración sorprendentes, lo que permite que su negocio permanezca en el borde de la competencia.

## <a name="adopt-a-methodical-approach"></a>Adoptar un enfoque metódico

La mayoría de los desafíos que he experimentado con la implementación de la seguridad en la nube en diferentes organizaciones, independientemente del sector, han sido muy similares. En primer lugar, aunque hay una gran cantidad de documentación excelente sobre funciones y características específicas, hay un nivel de confusión en el nivel de organización sobre lo que se aplica a ellas, dónde se superponen las características de seguridad y cómo se deben integrar las capacidades. También existe un nivel de duda sobre qué características de seguridad están preconfiguradas y cuáles requieren la configuración de la organización. Además, los equipos de soC desafortunadamente no han tenido la exposición completa, la formación o la asignación de presupuesto necesaria para prepararse para la rápida adopción de la nube y la transformación digital que ya están experimentando sus organizaciones.

Para ayudarle a eliminar estos obstáculos, Microsoft ha seleccionado varios recursos diseñados para ayudarle a tomar un enfoque metódico de su estrategia e implementación de seguridad.

|Resource   |Más información  |
|---------|---------|
|[Las tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](../security/top-security-tasks-for-remote-work.md)      | Si de pronto se encuentra con la ayuda de un personal que trabaja en casa principalmente, este artículo le ayuda a aumentar la seguridad rápidamente. Incluye las tareas recomendadas principales en función del plan de licencias.    |
|[Responsables de la toma de decisiones de seguridad de Microsoft 365](../security/Microsoft-365-security-for-bdm.md)    | Cuando tenga tiempo para un plan más completo, este artículo incluye recomendaciones que abarcan Microsoft 365, priorizado por superficie de ataque. Incluso viene con una hoja de cálculo que puedes usar para ordenar las licencias y el área (como la identidad, la protección contra amenazas y la supervisión).  |
|[Recomendaciones de arquitectura de seguridad de Microsoft](https://docs.microsoft.com/security/compass/compass)    | Si es un arquitecto de seguridad, asegúrese de ver las recomendaciones de seguridad organizadas por disciplina, incluidas las operaciones de identidad, redes y seguridad.   |
|[Recomendaciones de operaciones de seguridad de Microsoft](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Obtenga información sobre las recomendaciones de Microsoft para configurar y ejecutar un Centro de operaciones de seguridad (SOC) |
|[Curso práctico del Director de seguridad de la información (CISO)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Si no está seguro de la seguridad en la nube, no se pierda esta serie de vídeos.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Guía técnica de Microsoft para la estrategia de seguridad y la arquitectura.        |
| | |

Todos estos recursos están diseñados para usarse como punto de partida y adaptarse a las necesidades de su organización.
