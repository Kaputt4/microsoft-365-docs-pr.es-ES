---
title: 'Microsoft 365 Enterprise planeamiento de recursos: arquitectura de ciberseguridad'
description: Obtenga información sobre cómo superar los desafíos de seguridad en la arquitectura de Microsoft Enterprise de Kozeta Garrett, arquitecto de ciberseguridad de Microsoft.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 1b90b08218fff22c864b1307a3312eeff9bae003
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67586520"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Obstáculos de seguridad por los que puede navegar: punto de vista de un arquitecto

En este artículo, [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), arquitecto de ciberseguridad de Microsoft, describe los principales desafíos de seguridad que encuentra en las organizaciones empresariales y recomienda enfoques para navegar sobre estos obstáculos.

## <a name="about-the-author"></a>Acerca del autor

![Foto de Kozeta Garrett.](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

En mi rol de arquitecto de seguridad en la nube, he trabajado con varias organizaciones para proporcionar orientación estratégica y técnica centrada en diseñar e implementar la arquitectura de seguridad para los clientes que migran a Microsoft 365 y Azure, desarrollar soluciones de seguridad empresariales y ayudar a transformar la arquitectura de seguridad y la cultura para la resistencia empresarial. Mi experiencia incluye la detección y respuesta de incidentes, el análisis de malware, las pruebas de penetración y la recomendación de mejoras en la seguridad de TI y la posición de defensa. Me apasionan las transformaciones líderes que dan lugar a la seguridad como un facilitador para el negocio, incluidos los esfuerzos de modernización.

Ha sido muy satisfactorio ver cómo las organizaciones que adoptaron una mentalidad de modernización de seguridad en los últimos dos años se encuentran en una excelente posición que les permite seguir funcionando de forma remota de forma segura, a pesar de la reciente situación de COVID-19. Desafortunadamente, estas circunstancias también han servido como una llamada de reactivación para algunos clientes, que no estaban preparados para esta necesidad inmediata. Muchas organizaciones se dan cuenta de que deben modernizarse rápidamente, retirar su deuda de seguridad de TI acumulada y mejorar su posición de seguridad de la noche a la mañana para que puedan operar en estas circunstancias extremadamente inusuales.

La buena noticia es que Microsoft ha seleccionado algunos recursos excelentes para ayudar a las organizaciones a aumentar rápidamente su posición de seguridad. Además de estos recursos, me gustaría compartir los principales desafíos que he encontrado con los clientes a diario con la esperanza de que pueda navegar sobre estos obstáculos.

Actualmente vivo en el norte de Virginia, cerca de la capital de nuestro país, Washington DC. Me encanta todo tipo de actividades al aire libre y ejercicio, como correr, andar en bicicleta, hacer senderismo y nadar. Para contrarrestar estos me gusta tanto cocinar, comida gourmet, y viajar.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Asociarse con el equipo de seguridad desde el inicio de la adopción de la nube

Para empezar, no puedo enfatizar lo importante que es que los equipos de su organización se coordinen desde el principio. Los equipos de seguridad deben adoptarse como asociados críticos en las primeras fases de adopción y diseño de la nube. Esto significa que los equipos de seguridad se incorporan para defender la adopción de la nube, no solo para las funcionalidades agregadas a la empresa (como una gran experiencia de usuario desde dispositivos móviles seguros, aplicaciones de funcionalidad completa o creación de valor en los datos corporativos más allá de las limitadas funcionalidades de correo electrónico y aplicaciones de productividad), sino también para aprovechar las funcionalidades de almacenamiento, inteligencia artificial y análisis informático que ayudan a resolver los desafíos de seguridad nuevos y antiguos. Los equipos de seguridad deben estar incluidos en la administración de todos los aspectos de este cambio, incluidas las personas (cultura), los procesos (entrenamiento) y la tecnología para tener éxito. También significa invertir en la modernización y mejora continua del Centro de Operaciones de Seguridad (SOC). Trabaje juntos para alinear su estrategia de seguridad con la estrategia empresarial y las tendencias del entorno para asegurarse de que la transformación digital se realiza de forma segura. Cuando esto se hace bien, las organizaciones desarrollan la capacidad de adaptarse más rápido a los cambios, incluidos los cambios en la empresa, ti y seguridad.

Donde veo a los clientes superar los obstáculos más es cuando no hay ninguna asociación real entre las operaciones y los equipos de SOC. Aunque se presiona al equipo de operaciones y se le exige unas fechas límite estrictas para adoptar la nube, los equipos de seguridad no siempre se incluyen al principio del proceso para revisar y planear una estrategia de seguridad completa. Esto implica la integración de diferentes componentes en la nube y componentes locales. Esta falta de asociación se reduce aún más a los distintos equipos que parecen trabajar en silos para implementar controles para sus componentes específicos, lo que conduce a la complejidad adicional de la implementación, la solución de problemas y la integración.

Los clientes que navegan por estos obstáculos tienen buenas asociaciones entre las operaciones y la gobernanza y los equipos de administración de seguridad y riesgo para mejorar la estrategia de seguridad y los requisitos para proteger las cargas de trabajo de nube híbrida. Se centran en los objetivos y resultados finales de seguridad: protección de datos y disponibilidad de sistemas y servicios de acuerdo con los requisitos de gobernanza, riesgo y cumplimiento de la ciberseguridad. Estas organizaciones desarrollan asociaciones en fase temprana entre su equipo de operaciones y gobernanza y SOC, que es fundamental para el enfoque de diseño de seguridad y maximizará el valor de sus inversiones.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Creación de un perímetro de seguridad moderno (basado en identidad)

A continuación, adopte un enfoque de arquitectura Confianza cero. Esto comienza con la creación de un perímetro de seguridad moderno basado en identidades. Diseñe la arquitectura de seguridad en la que todos los intentos de acceso, ya sean locales o en la nube, se traten como no confiables hasta que se comprueben: "nunca confíen, comprueben siempre". Este enfoque de diseño no solo aumenta la seguridad y la productividad, sino que también permite a los usuarios trabajar desde cualquier lugar con cualquier tipo de dispositivo. Los sofisticados controles en la nube incluidos con Microsoft 365 le ayudan a proteger las identidades de los usuarios al tiempo que controlan el acceso a recursos valiosos en función del nivel de riesgo del usuario.

Para obtener una configuración recomendada, consulte [Configuraciones de acceso a dispositivos y identidades](../security/office-365-security/microsoft-365-policies-configurations.md).

## <a name="transition-security-controls-to-the-cloud"></a>Transición de controles de seguridad a la nube

Muchos equipos de seguridad siguen usando los procedimientos recomendados de seguridad tradicionales creados para todo el mundo local, incluido el mantenimiento de una "seguridad perimetral de red" y el intento de "forzar" las herramientas y controles de seguridad locales a las soluciones en la nube. Estos controles no se diseñaron para la nube, son ineficaces y dificultan la adopción de las funcionalidades modernas de la nube. Los procesos y las herramientas que funcionan para un enfoque de seguridad perimetral de red han demostrado ser ineficaces, obstruccionar las funcionalidades en la nube y no permiten aprovechar las características de seguridad modernas y automatizadas.

Para superar este obstáculo, cambie las estrategias de defensa a la protección administrada por la nube, la investigación y corrección automatizadas, las pruebas de lápiz automatizadas, la Defender para Office 365 y el análisis de incidentes. Los clientes que usan soluciones modernas de administración de dispositivos han implementado la administración automatizada, la aplicación de revisiones estandarizada, el antivirus, el cumplimiento de directivas y la protección de aplicaciones en todos los dispositivos (ya sea un teléfono inteligente, un equipo personal, un portátil o una tableta). Esto elimina la necesidad de una VPN, microsoft System Center Configuration Manager (SCCM) y directivas de grupo de Active Directory. Esto, combinado con las directivas de acceso condicional, proporciona un control y visibilidad eficaces, así como un acceso simplificado a los recursos independientemente del lugar desde el que operan sus usuarios.

## <a name="strive-for-best-together-security-tools"></a>Esforzarse por las herramientas de seguridad "mejores juntos"

Otro obstáculo que veo que los clientes tropiezan es adoptar un enfoque de "lo mejor de la raza" para las herramientas de seguridad. La creación continua de soluciones puntuales "mejores de raza" para abordar las necesidades de seguridad emergentes hace que la seguridad empresarial se desciborde. Incluso con las mejores intenciones, las herramientas de la mayoría de los entornos no se integran porque se vuelven demasiado costosas y complejas. Esto, a su vez, crea brechas de visibilidad, ya que hay más alertas para evaluar de lo que el equipo puede controlar. Volver a entrenar al equipo de SecOps en nuevas herramientas también se convierte en un desafío constante.

El enfoque "simple es mejor" también funciona para la seguridad. En lugar de ir detrás de las herramientas "mejores de la raza", navegue sobre este obstáculo mediante la adopción de una estrategia "mejor juntos" con herramientas que funcionan juntos de forma predeterminada. Las funcionalidades de seguridad de Microsoft protegen toda la organización con protección contra amenazas integrada que abarca aplicaciones, usuarios y nubes. La integración permite que una organización sea más resistente y reduzca el riesgo al contener atacantes en la entrada y corregir rápidamente los ataques.

## <a name="balance-security-with-functionality"></a>Equilibrio de la seguridad con la funcionalidad

Como vengo de una larga experiencia y experiencia en ciberseguridad, tiendo a preferir empezar con la configuración más segura de fábrica y permitir a las organizaciones relajar las configuraciones de seguridad en función de sus necesidades operativas y de seguridad. Sin embargo, esto puede llegar a un precio muy alto por la pérdida de funcionalidad y la mala experiencia del usuario. Como han aprendido muchas organizaciones, si la seguridad es demasiado difícil para los usuarios, encontrarán una manera de solucionarlo, incluido el uso de servicios en la nube no administrados. Por difícil que sea para mí aceptar, me he dado cuenta de que se debe lograr el delicado equilibrio entre funcionalidad y seguridad.

Las organizaciones que se dan cuenta de que los usuarios harán lo que sea necesario para realizar sus trabajos reconocen que la "batalla de SHADOW IT" no merece la pena luchar. Reconocen que los empleados de TI son los mayores delincuentes cuando se trata de Shadow IT y el uso de aplicaciones SaaS no aprobadas para su trabajo. Han cambiado su estrategia para fomentar su uso (en lugar de suprimir) y centrarse en mitigar los riesgos que podría crear. Los equipos de seguridad de esta organización no insisten en que todo se bloquee, registre y envíe a través de un proxy inverso o una VPN. En su lugar, estos equipos de seguridad duplican sus esfuerzos para proteger los datos valiosos y confidenciales de que se expongan a las partes equivocadas o a aplicaciones malintencionadas. Funcionan para proteger la integridad de los datos. Están haciendo uso completo de funcionalidades más avanzadas de protección de la información en la nube, incluido el cifrado, la autenticación multifactor segura, el riesgo y el cumplimiento automatizados, y las funcionalidades del agente de seguridad de acceso a la nube (CASB), al tiempo que permiten e incluso fomentan el uso compartido protegido en varias plataformas. Están convirtiendo shadow IT en creatividad, productividad y colaboración inspiradoras, lo que permite a su negocio mantenerse en la ventaja competitiva.

## <a name="adopt-a-methodical-approach"></a>Adopción de un enfoque metódico

La mayoría de los desafíos que he experimentado con la implementación de la seguridad en la nube en diferentes organizaciones, independientemente del sector, han sido muy similares. En primer lugar, aunque hay mucha documentación excelente sobre funcionalidades y características específicas, hay un nivel de confusión en el nivel de la organización sobre lo que se aplica a ellos, dónde se superponen las características de seguridad y cómo se deben integrar las funcionalidades. También hay un nivel de incertidumbre sobre qué características de seguridad se configuran previamente y cuáles requieren la configuración de la organización. Además, por desgracia, los equipos de SOC no han tenido la exposición completa, la formación o la asignación presupuestaria necesaria para prepararse para la rápida adopción de la nube y la transformación digital que sus organizaciones ya están experimentando.

Para ayudarle a superar estos obstáculos, Microsoft ha seleccionado varios recursos diseñados para ayudarle a adoptar un enfoque metódico para la estrategia de seguridad y la implementación.

|Recurso   |Más información  |
|---------|---------|
|[Las tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](../security/top-security-tasks-for-remote-work.md)      | Si se encuentra de repente apoyando a una fuerza de trabajo principalmente en el hogar, este artículo le ayuda a aumentar la seguridad rápidamente. Incluye las principales tareas recomendadas en función del plan de licencias.    |
|[Plan de implementación de Confianza cero de Microsoft 365](../security/microsoft-365-zero-trust.md)    | En este artículo se proporciona un plan de implementación para compilar Confianza cero seguridad con Microsoft 365. Incluye un póster descargable que puede usar para realizar un seguimiento de su progreso. |
|[Centro de orientación de confianza cero](/security/zero-trust/)  | Obtenga información sobre el modelo de seguridad de Confianza cero, sus principios y cómo implementar una arquitectura de Confianza cero mediante los planes de implementación. |
|[docs.security.com/security](/security/)    | Guía técnica de Microsoft para la arquitectura y la estrategia de seguridad.        |
| | |

Todos estos recursos están diseñados para usarse como punto de partida y adaptarse a las necesidades de su organización.
