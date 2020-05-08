---
title: 'Obstáculos de seguridad que puede gobernar: el punto de vista de un arquitecto'
description: Descripción.
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: eb8019efb13a13b27a67d541ae69ca6f30b35ed0
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160056"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Obstáculos de seguridad que puede gobernar: el punto de vista de un arquitecto

En este artículo, [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cybersecurity Architect en Microsoft, describe los principales desafíos de seguridad que encuentra en las organizaciones empresariales y recomienda enfoques para navegar por estos obstáculos. 

## <a name="about-the-author"></a>Acerca del autor

![Foto de Kozeta Garrett](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

En mi rol como arquitecto de seguridad en la nube, he trabajado con varias organizaciones para proporcionar orientación estratégica y técnica centrada en el diseño y la implementación de la arquitectura de seguridad para los clientes que migren a Microsoft 365 y Azure, desarrollen soluciones de seguridad empresarial y ayuden a transformar la arquitectura de seguridad y la cultura para la resistencia empresarial. Mi experiencia incluye la detección y respuesta de incidentes, el análisis de malware, las pruebas de penetración y la recomendación de mejoras en la seguridad y la actitud de ti. Estoy muy entusiasmado con las transformaciones iniciales que resultan en la seguridad como un habilitador para la empresa, incluidos los esfuerzos de modernización.

Ha sido más satisfactorio para ver cómo las organizaciones que adoptaron una mental? a modernización de seguridad durante los últimos dos años están en una posición muy importante que les permite seguir funcionando de forma remota de manera segura, a pesar de la reciente COVID-19. Desafortunadamente, estas circunstancias también se han atendido como una llamada de activación para algunos clientes, que no están preparadas para esta necesidad inmediata. Muchas organizaciones están dando por hecho que deben modernizarse rápidamente, retirar la deuda de seguridad de ti acumulada y mejorar su postura de seguridad durante la noche para que puedan operar en estas circunstancias muy inusuales.

La buena noticia es que Microsoft ha creadosdo algunos recursos excelentes para ayudar a las organizaciones a aumentar rápidamente su postura de seguridad. Además de estos recursos, me gustaría compartir los principales desafíos que he encontrado con los clientes a diario con la esperanza de que pueda gobernar estos obstáculos.

Actualmente vive en Virginia del norte, cerca del capital de nuestro país, Washington DC. Me encanta casi todos los formularios de actividades exteriores y el ejercicio, como la ejecución, el Hiking de la mano y el natación. Para contrarrestar estas cosas, disfrute de la misma comida, comida de gourmet y viajes. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Asociado con el equipo de seguridad desde el inicio de la adopción de la nube

Para empezar, no puedo enfatizar lo bastante importante para que los equipos de la organización coordinen desde el principio. Los equipos de seguridad deben adoptarse como socios críticos en las primeras etapas de la adopción y el diseño de la nube. Esto significa obtener equipos de seguridad integrados en la adopción de la nube de Champions, no solo para las capacidades agregadas a la empresa (como una excelente experiencia de usuario desde dispositivos móviles seguros, aplicaciones de funcionalidad completa o la creación de valor en datos corporativos más allá de las aplicaciones de correo electrónico y productividad limitadas), sino también para aprovechar las capacidades de análisis de almacenamiento, AI y cómputo. Los equipos de seguridad deben incluirse en la administración de todos los aspectos de este cambio, incluidos los usuarios (cultura), los procesos (formación) y la tecnología que se debe realizar correctamente. También implica invertir en modernización y mejora continua del centro de operaciones de seguridad (SOC). Trabaje conjuntamente para alinear su estrategia de seguridad con la estrategia empresarial y las tendencias del entorno para asegurarse de que la transformación digital se realiza de forma segura. Cuando esto se hace bien, las organizaciones desarrollan la capacidad para adaptarse más rápidamente a los cambios, incluidos los cambios en el negocio, la TI y la seguridad. 

Donde veo que los clientes se desplazan más por obstáculos cuando no hay ninguna asociación real entre las operaciones y los equipos de SOC. Mientras que el equipo de operaciones está sometido a presiones y fechas con plazos ajustados para adoptar la nube, los equipos de seguridad no siempre se incluyen en las primeras fases del proceso de revisión y planeación de una estrategia de seguridad global. Esto implica la integración de diferentes componentes de la nube y componentes locales. Esta falta de asociación complica aún más a diferentes equipos que parecen trabajar en silos para implementar controles para sus componentes específicos, lo que lleva a la complejidad agregada de implementación, solución de problemas e integración.

Los clientes que enarbolen estos obstáculos tienen buenas asociaciones entre las operaciones y el gobierno y los equipos de administración de riesgos y seguridad para renovar la estrategia de seguridad y los requisitos para proteger las cargas de trabajo de la nube híbrida. Se centran en las metas y los resultados finales de seguridad: la protección de datos y la disponibilidad de servicios y sistemas según los requisitos de gobierno, riesgo y cumplimiento normativo de Cybersecurity. Estas organizaciones desarrollan asociaciones tempranas entre sus operaciones y su equipo de gobierno y gobernanza, lo cual es fundamental para el enfoque de diseño de seguridad y maximizará el valor de sus inversiones. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Crear un perímetro de seguridad moderno (basado en la identidad)

A continuación, adopte un enfoque de arquitectura de confianza cero. Esto comienza con la creación de un perímetro moderno de seguridad basado en identidades. Diseñar la arquitectura de seguridad en la que cada intento de acceso, ya sea local o en la nube, se trate como no de confianza hasta que se compruebe: "no confiar, siempre comprobar". Este método de diseño no solo aumenta la seguridad y la productividad, sino que también permite a los usuarios trabajar desde cualquier lugar con cualquier tipo de dispositivo. Los sofisticados controles de nube incluidos con Microsoft 365 ayudan a proteger las identidades de los usuarios a la vez que controlan el acceso a recursos valiosos en función del nivel de riesgo del usuario.

Para una configuración recomendada, consulte [Identity and Device Access](../enterprise/microsoft-365-policies-configurations.md)Configurations. 

## <a name="transition-security-controls-to-the-cloud"></a>Controles de seguridad de transición a la nube

Muchos equipos de seguridad siguen usando los procedimientos recomendados de seguridad tradicionales creados para todo el mundo local, incluido el mantenimiento de un "seguridad del perímetro de red" e intentan "forzar" las herramientas de seguridad locales y los controles para las soluciones de nube. Estos controles no se diseñaron para la nube, son ineficaces y dificultan la adopción de capacidades de nube modernas. Los procesos y las herramientas que funcionan para un enfoque de seguridad del perímetro de red han demostrado ser ineficaces, Obstructive a las capacidades de la nube y no permiten aprovechar las características de seguridad modernas y automatizadas.

Puede gobernar este obstáculo mediante la transición de las estrategias de defensa a la protección administrada en la nube, la investigación y la corrección automatizadas, las pruebas automáticas de lápiz, la protección contra amenazas avanzada y el análisis de incidentes. Los clientes que usan soluciones modernas de administración de dispositivos han implementado la administración automatizada, la revisión estandarizada, el antivirus, el cumplimiento de directivas y la protección de aplicaciones en todos los dispositivos (ya sea un smartphone, un ordenador personal, un portátil o una tableta). Esto elimina la necesidad de una VPN, Microsoft System Center Configuration Manager (SCCM) y las directivas de grupo de Active Directory. Esto, combinado con las directivas de acceso condicional, proporciona un control y una visibilidad potentes, así como un acceso optimizado a los recursos independientemente de dónde estén funcionando sus usuarios.

## <a name="strive-for-best-together-security-tools"></a>Lucha por las mejores herramientas de seguridad

Otro obstáculo en el que veo a los clientes Stumble es tomar un enfoque de "mejor calidad" para las herramientas de seguridad. La organización continua en capas de soluciones puntuales de "mejor raza" para abordar las necesidades de seguridad emergentes hace que la seguridad de la empresa se desglose. Incluso con las mejores intenciones, las herramientas de la mayoría de los entornos no se integran porque se convierten en demasiado caros y complejos. Esto, a su vez, crea brechas en la visibilidad a medida que hay más alertas para evaluar de las que el equipo puede controlar. Volver a entrenar al equipo de SecOps en nuevas herramientas también se convierte en un reto constante.

El enfoque "sencillo es mejor" también es compatible con la seguridad. En lugar de ir después de las herramientas "Best of raza", Enarbolemos este obstáculo adoptando una estrategia "mejor" con herramientas que funcionen juntos de forma predeterminada. Las funciones de seguridad de Microsoft protegen a toda la organización con una protección de amenazas integrada que abarque las aplicaciones, los usuarios y las nubes. La integración permite a una organización ser más resistente y reducir el riesgo al contener a los atacantes en la entrada y corregir los ataques rápidamente.

## <a name="balance-security-with-functionality"></a>Equilibrio entre la seguridad y la funcionalidad

A medida que proviene de un Cybersecurity de antecedentes y experiencia, me gustaría comenzar con la configuración más segura de forma rápida y permitir a las organizaciones relajar las configuraciones de seguridad en función de sus necesidades operativas y de seguridad. Sin embargo, esto puede supartir un precio muy elevado de funcionalidad perdida y una mala experiencia del usuario. Como muchas organizaciones han aprendido, si la seguridad es demasiado difícil para los usuarios, encontrará una forma de evitarlo, incluido el uso de servicios en la nube no administrados. Como es para que la acepte, me he dado cuenta de que se debe lograr la funcionalidad delicada-equilibrio de seguridad.

Las organizaciones que se dan a los usuarios haciendo lo que se necesita para realizar su trabajo reconocen que la "batalla" de ti no merece la pena luchar. Reconocen que los empleados de TI son los principales infractores cuando se trata de sombrearlos y el uso de aplicaciones de SaaS no aprobadas para su trabajo. Han desplazado su estrategia para fomentar su uso (en lugar de suprimir) y centrarse en mitigar la exposición a los riesgos que podría crear. Estos equipos de seguridad de la organización no insisten en que todo se bloquea, se registra y se envía a través de un proxy inverso o VPN. En su lugar, estos equipos de seguridad duplican sus esfuerzos para proteger los datos confidenciales y valiosos que se exponen a las partes equivocadas o a las aplicaciones malintencionadas. Trabajan para proteger la integridad de los datos. Están haciendo un uso completo de las funcionalidades más avanzadas de protección de la información de la nube, como el cifrado, la autenticación multifactor segura, el cumplimiento y el riesgo automatizado, y las capacidades del agente de seguridad de aplicaciones en la nube (CASB), al tiempo que permiten e incluso fomentan el uso compartido protegido en varias plataformas Están convirtiéndolos en una instantánea de la creatividad, la productividad y la colaboración, lo que permite que su negocio permanezca en el perímetro competitivo.


## <a name="adopt-a-methodical-approach"></a>Adoptar un enfoque metódico 

La mayoría de los desafíos que he experimentado al implementar la seguridad en la nube en diferentes organizaciones, independientemente de la industria, han sido muy similares. En primer lugar, si bien hay una gran cantidad de documentación muy amplia sobre capacidades y características específicas, hay un nivel de confusión en el nivel de la organización sobre lo que les aplica, dónde se superponen las características de seguridad y cómo deben integrarse las capacidades. También hay un nivel de incertidumbre sobre las características de seguridad que vienen preconfiguradas y que requieren la configuración por parte de la organización. Además, los equipos de SOC desgraciaó la exposición total, la formación o la asignación del presupuesto necesaria para prepararse para la rápida adopción de la nube y la transformación digital sus organizaciones ya están en curso.

Para ayudarle a borrar estos obstáculos, Microsoft ha creados varios recursos diseñados para ayudarle a tomar un enfoque metódico en su estrategia de seguridad e implementación. 


|Resource   |Más información  |
|---------|---------|
|[Principales tareas para que los equipos de seguridad admitan el trabajo desde casa](../security/top-security-tasks-for-remote-work.md)      | Si se ve que, de repente, admite un personal de trabajo en casa principalmente, este artículo le ayudará a incrementar la seguridad rápidamente. Incluye las principales tareas recomendadas basadas en el plan de licencias.    |
|[Microsoft 365 Security para responsables de decisiones empresariales](../security/Microsoft-365-security-for-bdm.md)    | Cuando tiene tiempo para un plan más completo, este artículo incluye recomendaciones que abarcan Microsoft 365, con prioridades por superficie de ataques. Incluye incluso una hoja de cálculo que puede usar para ordenar la licencia y el área (por ejemplo, identidad, protección contra amenazas y supervisión).  |
|[Recomendaciones de la arquitectura de seguridad de Microsoft](https://docs.microsoft.com/security/compass/compass)    | Si es un arquitecto de seguridad, asegúrese de ver las recomendaciones de seguridad organizadas por disciplina, incluidas las operaciones de identidad, red y seguridad.   |
|[Recomendaciones de operaciones de seguridad de Microsoft](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Obtener recomendaciones de Microsoft para configurar y ejecutar un centro de operaciones de seguridad (SOC) |
|[Formación del taller Chief Information Security Office (CISO)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Si no está familiarizado con la seguridad en la nube, no pierda esta serie de vídeos.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Orientación técnica de Microsoft sobre la estrategia de seguridad y la arquitectura.        |
| | |

Todos estos recursos están diseñados para su uso como punto de partida y se adaptan a las necesidades de su organización. 

