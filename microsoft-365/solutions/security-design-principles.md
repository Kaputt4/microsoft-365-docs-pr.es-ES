---
title: 'Planeación de recursos de Microsoft 365 Enterprise: arquitectura de ciberseguridad'
description: Obtenga información sobre cómo superar los desafíos de seguridad en la arquitectura de Microsoft Enterprise de Kozeta Garrett, Cybersecurity Architect en Microsoft.
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
ms.openlocfilehash: 7cd9098766024093a0b9fa2d6e95131bf13d09df
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052487"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Obstáculos de seguridad por los que puede navegar: el punto de vista de un arquitecto

En este artículo, [Kozeta Garrett,](https://www.linkedin.com/in/kozeta-garrett-53013a6/)Cybersecurity Architect en Microsoft, describe los principales desafíos de seguridad que encuentra en organizaciones empresariales y recomienda métodos para navegar por estos obstáculos.

## <a name="about-the-author"></a>Acerca del autor

![Foto de KozetaRetret](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

En mi rol como arquitecto de seguridad en la nube, he trabajado con varias organizaciones para proporcionar instrucciones estratégicas y técnicas centradas en diseñar e implementar la arquitectura de seguridad para los clientes que migran a Microsoft 365 y Azure, desarrollan soluciones de seguridad empresariales y ayudan a transformar la arquitectura de seguridad y la cultura para la resistencia empresarial. Mi experiencia incluye la detección y respuesta de incidentes, el análisis de malware, las pruebas de penetración y la recomendación de mejoras en la posición de seguridad y defensa de IT. Me apasionan las transformaciones líderes que resultan en la seguridad como un habilitador para la empresa, incluidos los esfuerzos de modernización.

Ha sido MUY satisfactorio ver cómo las organizaciones que adoptaron una mentalidad de modernización de seguridad en los últimos dos años se encuentran en una excelente posición que les permite seguir funcionando de forma remota de forma segura, a pesar de la reciente situación de COVID-19. Desafortunadamente, estas circunstancias también han servido como una llamada de atención para algunos clientes, que no estaban listos para esta necesidad inmediata. Muchas organizaciones se están dando cuenta de que deben modernizarse rápidamente, retirar la deuda de seguridad de TI acumulada y mejorar su posición de seguridad durante la noche para que puedan operar en estas circunstancias extremadamente inusuales.

La buena noticia es que Microsoft ha seleccionado algunos recursos excelentes para ayudar a las organizaciones a aumentar rápidamente su posición de seguridad. Además de estos recursos, me gustaría compartir los principales desafíos que he encontrado con los clientes diariamente con la esperanza de que pueda navegar por estos obstáculos.

Actualmente vivo en el norte de Virginia, cerca de la capital de nuestro país, Washington DC. Me encantan casi todas las actividades al aire libre y el ejercicio, como correr, andar en bicicleta, hacer senderismo y natación. Para hacer frente a estos, me gusta tanto cocción, comidas gastrónomos y viajes.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Asociarse con el equipo de seguridad desde el inicio de la adopción en la nube

Para empezar, no puedo enfatizar lo suficientemente importante que los equipos de su organización coordinen desde el principio. Los equipos de seguridad deben adoptarse como socios críticos en las primeras etapas de la adopción y el diseño de la nube. Esto significa que los equipos de seguridad se incorporen a la adopción de la nube, no solo para las capacidades agregadas a la empresa (como una gran experiencia de usuario desde dispositivos móviles seguros, aplicaciones de funcionalidad completa o creación de valor en datos corporativos más allá de las aplicaciones de productividad y correo electrónico de funcionalidad limitada), sino también para aprovechar las capacidades de almacenamiento, inteligencia artificial y análisis informático que ayudan a resolver nuevos y antiguos desafíos de seguridad. Los equipos de seguridad deben incluirse en la administración de todos los aspectos de este turno, incluidas las personas (cultura), los procesos (formación) y la tecnología para que sean correctos. También significa invertir en la modernización y mejora continua del Centro de operaciones de seguridad (SOC). Trabaje juntos para alinear su estrategia de seguridad con las tendencias de su estrategia empresarial y entorno para garantizar que la transformación digital se realiza de forma segura. Cuando esto se hace bien, las organizaciones desarrollan la capacidad de adaptarse más rápido a los cambios, incluidos los cambios en la empresa, TI y seguridad.

Donde más veo que los clientes se lanzan a través de obstáculos es cuando no hay una asociación real entre las operaciones y los equipos de SOC. Mientras el equipo de operaciones está siendo presionado y con plazos ajustados para adoptar la nube, los equipos de seguridad no siempre se incluyen al principio del proceso para revisar y planear una estrategia de seguridad completa. Esto implica la integración de componentes y componentes de nube diferentes de forma previa. Esta falta de asociación se abate aún más a diferentes equipos que parecen funcionar en silos para implementar controles para sus componentes específicos, lo que lleva a la complejidad agregada de implementación, solución de problemas e integración.

Los clientes que navegan por estos obstáculos tienen buenas asociaciones entre las operaciones y el gobierno y los equipos de administración de seguridad y riesgos para renovar la estrategia de seguridad y los requisitos para proteger las cargas de trabajo de nube híbrida. Se centran en los objetivos y resultados de seguridad finales: protección de datos y disponibilidad de sistemas y servicios de acuerdo con los requisitos de gobierno, riesgo y cumplimiento de ciberseguridad. Estas organizaciones desarrollan asociaciones de fase temprana entre su equipo de operaciones y gobierno y SOC, lo que es fundamental para el enfoque de diseño de seguridad y maximizará el valor de sus inversiones.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Crear un perímetro de seguridad moderno (basado en identidades)

A continuación, adopte un enfoque de arquitectura de confianza cero. Esto comienza con la creación de un perímetro de seguridad moderno basado en identidades. Diseñe la arquitectura de seguridad en la que cada intento de acceso, ya sea local o en la nube, se trate como no confiable hasta que se compruebe: "nunca confíe, compruebe siempre". Este enfoque de diseño no solo aumenta la seguridad y la productividad, sino que también permite a los usuarios trabajar desde cualquier lugar con cualquier tipo de dispositivo. Los sofisticados controles en la nube incluidos con Microsoft 365 le ayudan a proteger las identidades de los usuarios al tiempo que controlan el acceso a recursos valiosos en función del nivel de riesgo del usuario.

Para obtener una configuración recomendada, consulte [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).

## <a name="transition-security-controls-to-the-cloud"></a>Transición de controles de seguridad a la nube

Muchos equipos de seguridad siguen usando los procedimientos recomendados de seguridad tradicionales creados para un mundo local, como mantener una "seguridad perimetral de red" e intentar "forzar" las herramientas de seguridad y los controles locales a las soluciones en la nube. Estos controles no se diseñaron para la nube, son ineficaces y dificultan la adopción de capacidades modernas en la nube. Los procesos y herramientas que funcionan para un enfoque de seguridad perimetral de red han demostrado ser ineficientes, obstruyen las capacidades de la nube y no permiten aprovechar las características de seguridad modernas y automatizadas.

Puede navegar por este obstáculo cambiando las estrategias de defensa a la protección administrada en la nube, la investigación automatizada y la corrección, las pruebas automáticas de lápiz, Defender para Office 365 y el análisis de incidentes. Los clientes que usan soluciones modernas de administración de dispositivos han implementado la administración automatizada, la revisión estandarizada, el antivirus, la aplicación de directivas y la protección de aplicaciones en todos los dispositivos (ya sea un smartphone, un equipo personal, un portátil o una tableta). Esto elimina la necesidad de una VPN, Microsoft System Center Configuration Manager (SCCM) y directivas de grupo de Active Directory. Esto, combinado con las directivas de acceso condicional, proporciona un control y una visibilidad eficaces, así como un acceso simplificado a los recursos independientemente de dónde operan sus usuarios.

## <a name="strive-for-best-together-security-tools"></a>Buscar herramientas de seguridad "mejores juntos"

Otro obstáculo que veo que los clientes se tropiezan es tomar un enfoque de "lo mejor de la raza" para las herramientas de seguridad. La aplicación continua de soluciones de puntos de "lo mejor de la raza" para satisfacer las necesidades de seguridad emergentes hace que la seguridad empresarial se rompa. Incluso con las mejores intenciones, las herramientas de la mayoría de los entornos no se integran porque se vuelve demasiado costosa y compleja. Esto, a su vez, crea vacíos en la visibilidad, ya que hay más alertas de las que el equipo puede controlar. Volver a entrenar al equipo de SecOps en nuevas herramientas también se convierte en un desafío constante.

El enfoque "simple es mejor" también funciona para la seguridad. En lugar de buscar herramientas de "lo mejor de la raza", navega por este obstáculo adoptando una estrategia de "mejor juntos" con herramientas que funcionen juntas de forma predeterminada. Las capacidades de seguridad de Microsoft protegen toda la organización con una protección contra amenazas integrada que abarca aplicaciones, usuarios y nubes. La integración permite a una organización ser más resistente y reducir el riesgo al contener atacantes en la entrada y corregir rápidamente los ataques.

## <a name="balance-security-with-functionality"></a>Equilibrar la seguridad con la funcionalidad

A medida que procede de un largo historial y experiencia de ciberseguridad, suelo preferir empezar con la configuración más segura y permitir que las organizaciones relajen las configuraciones de seguridad en función de sus necesidades operativas y de seguridad. Sin embargo, esto puede llegar a un precio elevado de funcionalidad perdida y mala experiencia del usuario. Como muchas organizaciones han aprendido, si la seguridad es demasiado difícil para los usuarios, encontrarán una forma de trabajar alrededor de usted, incluido el uso de servicios en la nube no administrados. Tan difícil como para mí aceptar, he llegado a darme cuenta de que el equilibrio entre funcionalidad y seguridad delicado debe lograrse.

Las organizaciones que se dan cuenta de que los usuarios harán lo que sea necesario para realizar sus trabajos reconocen que la "batalla de TI de sombra" no vale la pena luchar. Reconocen que los empleados de TI son los mayores infractores cuando se trata de ti de instantánea y el uso de aplicaciones SaaS no aprobadas para su trabajo. Han cambiado su estrategia para fomentar su uso (en lugar de suprimir) y centrarse en mitigar los riesgos de exposición que podría crear. Los equipos de seguridad de esta organización no insisten en que todo se bloquee, se registra y se envíe a través de un proxy inverso o una VPN. En su lugar, estos equipos de seguridad duplican sus esfuerzos para proteger datos valiosos y confidenciales para que no se exponán a terceros incorrectos o aplicaciones malintencionadas. Trabajan para proteger la integridad de los datos. Están haciendo un uso completo de las capacidades más avanzadas de protección de la información en la nube, incluido el cifrado, la autenticación multifactor segura, el riesgo y el cumplimiento automatizados, y las capacidades de Cloud App Security Broker (CASB), al tiempo que permiten e incluso fomentan el uso compartido protegido en varias plataformas. Están convirtiendo la TECNOLOGÍA de la sombra en una creatividad, productividad y colaboración que les permite a su empresa mantenerse en el borde de la competencia.

## <a name="adopt-a-methodical-approach"></a>Adoptar un enfoque metódico

La mayoría de los desafíos que he experimentado con la implementación de la seguridad en la nube en diferentes organizaciones, independientemente de la industria, han sido muy similares. En primer lugar, aunque hay una gran documentación sobre funciones y características específicas, hay un nivel de confusión en el nivel de la organización sobre lo que se aplica a ellas, dónde se superponen las características de seguridad y cómo se deben integrar las capacidades. También existe un nivel de incertidumbre acerca de qué características de seguridad están preconfiguradas y cuáles requieren la configuración de la organización. Además, los equipos de SOC desafortunadamente no han tenido la exposición completa, la formación o la asignación presupuestada necesaria para prepararse para la rápida adopción de la nube y la transformación digital que ya están experimentando sus organizaciones.

Para ayudarle a eliminar estos obstáculos, Microsoft ha seleccionado varios recursos diseñados para ayudarle a tomar un enfoque metódico de la estrategia de seguridad y la implementación.

|Resource   |Más información  |
|---------|---------|
|[Las tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](../security/top-security-tasks-for-remote-work.md)      | Si de repente se encuentra con un equipo de trabajo en casa, este artículo le ayuda a aumentar la seguridad rápidamente. Incluye las tareas recomendadas más importantes en función del plan de licencias.    |
|[Microsoft 365 Security for Business Decisions Makers](../security/Microsoft-365-security-for-bdm.md)    | Cuando tienes tiempo para un plan más completo, este artículo incluye recomendaciones que abarcan Microsoft 365, priorizado por superficie de ataque. Incluso viene con una hoja de cálculo que puedes usar para ordenar las licencias y el área (como identidad, protección contra amenazas y supervisión).  |
|[Recomendaciones de arquitectura de seguridad de Microsoft](/security/compass/compass)    | Si es arquitecto de seguridad, asegúrese de ver las recomendaciones de seguridad organizadas por disciplina, incluidas las operaciones de identidad, redes y seguridad.   |
|[Recomendaciones de Operaciones de seguridad de Microsoft](/security/compass/security-operations-videos-and-decks)|Obtenga información sobre las recomendaciones de Microsoft para configurar y ejecutar un Centro de operaciones de seguridad (SOC) |
|[Formación del jefe de seguridad de la información (CISO)](/security/ciso-workshop/ciso-workshop)   | Si eres nuevo en la seguridad en la nube, no te pierdas esta serie de vídeos.        |
|[docs.security.com/security](/security/)    | Guía técnica de toda Microsoft para la estrategia de seguridad y la arquitectura.        |
| | |

Todos estos recursos están diseñados para usarse como punto de partida y adaptarse a las necesidades de su organización.