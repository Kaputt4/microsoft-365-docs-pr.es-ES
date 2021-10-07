---
title: Paso 1. Planear la preparación Microsoft 365 Defender operaciones
description: Los conceptos básicos de la planeación de Microsoft 365 Defender preparación de operaciones al integrar Microsoft 365 Defender en las operaciones de seguridad.
keywords: incidentes, alertas, investigar, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: db4b5b7518f3a79a37222764c0b7d627078aba5f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198006"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>Paso 1. Planear la preparación Microsoft 365 Defender operaciones

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Independientemente del vencimiento actual de las operaciones de seguridad, es importante que se alinee con el Centro de operaciones de seguridad (SOC). Aunque no hay un solo modelo que se adapte a todas las organizaciones, hay ciertos aspectos que son más comunes que otros. 

En las secciones siguientes se describen las funciones principales del SOC.

## <a name="provide-situational-awareness-of-modern-threats"></a>Proporcionar conciencia situacional de las amenazas modernas

Un equipo de SOC se prepara y busca amenazas nuevas y entrantes para que puedan trabajar con la organización para establecer contramedidas y respuestas. El equipo de SOC debe tener personal altamente formado en métodos y técnicas de ataque modernos y comprender los actores de amenazas. Los marcos y la inteligencia de amenazas compartidas, como la cadena [cyber kill](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/) o el marco de&CK de [MITRE ATT,](https://attack.mitre.org/) pueden capacitar a su personal de analistas de amenazas y cazadores de amenazas.

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>Proporcionar respuestas de primer, segundo y potencialmente de tercer nivel a incidentes y eventos cibernéticos

El SOC es la primera línea de defensa frente a eventos e incidentes de seguridad. Cuando un evento, una amenaza, un ataque, una infracción de directiva o un hallazgo de auditoría desencadenan una alerta o llamada a la acción, el equipo de SOC realiza una evaluación para evaluarla y contenerla o escalarla para su investigación. Por lo tanto, los respondedores de primera línea SOC deben tener un amplio conocimiento técnico de los eventos e indicadores de seguridad.

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>Centralizar la supervisión y el registro de los orígenes de seguridad de la organización 

Por lo general, la función principal del equipo soc es asegurarse de que todos los dispositivos de seguridad, como firewalls, sistemas de prevención de intrusiones, sistemas de prevención de pérdida de datos, sistemas de Administración de amenazas y vulnerabilidades y sistemas de identidad, funcionen correctamente y se supervisen. Los equipos soc trabajarán con las operaciones de red más amplias, como identidad, DevOps, nube, aplicación, ciencia de datos y otros equipos empresariales para garantizar que el análisis de la información de seguridad esté centralizado y protegido. Además, el equipo soc es responsable de mantener los registros de los datos en formatos utilizables y legibles, lo que podría incluir el análisis y normalización de formatos distintos.

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>Establecer preparación operativa del equipo rojo, azul y púrpura

Cada equipo de SOC debe probar su preparación para responder a un incidente cibernético. Las pruebas se pueden realizar a través de ejercicios de aprendizaje, como tablas superiores y ejecuciones de prácticas con varias personas en INFORMÁTICA, seguridad y a nivel empresarial. Los equipos de ejercicios de entrenamiento individuales se crean basándose en roles representativos y desempeñan el rol de un defensor (equipo azul), un atacante (equipo rojo) o como observadores que buscan mejorar los métodos y técnicas de los equipos azul y rojo a través de las fortalezas y debilidades que se descubren durante el ejercicio (equipo púrpura).

## <a name="next-step"></a>Paso siguiente

[Paso 2. Realizar una evaluación de preparación de integración SOC con el marco de confianza cero](integrate-microsoft-365-defender-secops-readiness.md)



