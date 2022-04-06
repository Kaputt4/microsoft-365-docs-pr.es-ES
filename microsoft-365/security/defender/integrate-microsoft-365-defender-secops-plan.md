---
title: Paso 1. Planear la preparación de las operaciones Microsoft 365 Defender
description: Los conceptos básicos de planeamiento de la preparación de las operaciones Microsoft 365 Defender al integrar Microsoft 365 Defender en las operaciones de seguridad.
keywords: incidentes, alertas, investigación, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8c69e92390e6ed6515be6f399703124ece99cc39
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664026"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>Paso 1. Planear la preparación de las operaciones Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Sea cual sea la madurez actual de las operaciones de seguridad, es importante que se alinee con el Centro de operaciones de seguridad (SOC). Aunque no hay ningún modelo único que se ajuste a todas las organizaciones, hay ciertos aspectos que son más comunes que otros.

En las secciones siguientes se describen las funciones principales del SOC.

## <a name="provide-situational-awareness-of-modern-threats"></a>Proporcionar una conciencia situacional de las amenazas modernas

Un equipo de SOC se prepara y busca amenazas nuevas y entrantes para que puedan trabajar con la organización para establecer contramedidas y respuestas. El equipo de SOC debe tener personal altamente entrenado en métodos y técnicas de ataque modernos y comprender a los actores de amenazas. La inteligencia y los marcos de amenazas compartidos, como [cyber kill chain](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/) o [MITRE ATT&marco de CK](https://attack.mitre.org/) , pueden capacitar al personal de analistas de amenazas y cazadores de amenazas.

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>Proporcionar respuestas de primer, segundo y potencialmente de tercer nivel a incidentes y eventos cibernéticos

El SOC es la primera línea de defensa frente a eventos e incidentes de seguridad. Cuando un evento, amenaza, ataque, infracción de directiva o búsqueda de auditoría desencadena una alerta o una llamada a la acción, el equipo de SOC realiza una evaluación para evaluar y contenerla o escalarla para su investigación. Por lo tanto, los respondedores de primera línea de SOC deben tener un amplio conocimiento técnico de los eventos e indicadores de seguridad.

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>Centralización de la supervisión y el registro de los orígenes de seguridad de la organización

Normalmente, la función principal del equipo de SOC es asegurarse de que todos los dispositivos de seguridad, como firewalls, sistemas de prevención de intrusiones, sistemas de prevención de pérdida de datos, sistemas de Administración de amenazas y vulnerabilidades y sistemas de identidad, funcionan correctamente y se supervisan. Los equipos de SOC trabajarán con las operaciones de red más amplias, como identidad, DevOps, nube, aplicación, ciencia de datos y otros equipos empresariales para garantizar que el análisis de la información de seguridad está centralizado y protegido. Además, el equipo de SOC es responsable de mantener los registros de los datos en formatos legibles y utilizables, lo que podría incluir el análisis y normalización de formatos dispares.

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>Establecimiento de la preparación operativa del equipo rojo, azul y púrpura

Cada equipo de SOC debe probar su preparación para responder a un incidente cibernético. Las pruebas se pueden realizar a través de ejercicios de entrenamiento, como tablas y ejecuciones de práctica con varias personas en TI, seguridad y en el nivel empresarial. Los equipos de ejercicios de entrenamiento individuales se crean en función de roles representativos y desempeñan el papel de un defensor (equipo azul), un atacante (equipo rojo) o como observadores que buscan mejorar los métodos y las técnicas de los equipos azul y rojo a través de puntos fuertes y débiles que se descubren durante el ejercicio (equipo púrpura).

## <a name="next-step"></a>Paso siguiente

[Paso 2. Realizar una evaluación de la preparación de integración de SOC mediante Confianza cero Framework](integrate-microsoft-365-defender-secops-readiness.md)
