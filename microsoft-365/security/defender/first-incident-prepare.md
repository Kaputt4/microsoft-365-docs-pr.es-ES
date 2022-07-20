---
title: Preparación de la posición de seguridad para el primer incidente
description: Configure la posición de seguridad del inquilino de Microsoft 365 para el primer incidente en Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
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
- m365solution-firstincident
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 690e1c48a452cfa00f0ae8d4fd87849b1c2e79dc
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "66893527"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Preparación de la posición de seguridad para el primer incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

La preparación para el control de incidentes implica la configuración de una protección suficiente de la red de una organización frente a distintos tipos de incidentes de seguridad. Para reducir el riesgo de incidentes de seguridad, el Instituto Nacional de Estándares y Tecnología (NIST) recomienda varias prácticas de seguridad, incluidas las evaluaciones de riesgos, la protección de la seguridad del host, la configuración de redes de forma segura y la prevención de malware.

Microsoft 365 Defender puede ayudar a abordar varios aspectos de la prevención de incidentes:

- Implementación de un marco [de Confianza cero](/security/zero-trust/)
- Determinación de la posición de seguridad mediante la asignación de una puntuación con [puntuación segura de Microsoft](microsoft-secure-score.md)
- Prevención de amenazas mediante evaluaciones de vulnerabilidades en [Administración de amenazas y vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Descripción de las amenazas de seguridad más recientes para que pueda prepararse para ellas con [el análisis de amenazas](threat-analytics.md)

## <a name="step-1-implement-zero-trust"></a>Paso 1. Implementación de Confianza cero

[Confianza cero](/security/zero-trust/) es una filosofía de seguridad integrada y una estrategia integral que tiene en cuenta la naturaleza compleja de cualquier entorno moderno, incluidos los empleados móviles y los usuarios, dispositivos, aplicaciones y datos, dondequiera que se encuentren. Al proporcionar un único panel de cristal para administrar todas las detecciones de forma coherente, Microsoft 365 Defender puede facilitar al equipo de operaciones de seguridad la implementación de [los principios rectores](/security/zero-trust/#guiding-principles-of-zero-trust) de Confianza cero.

Los componentes de Microsoft 365 Defender pueden mostrar infracciones de las reglas que se han implementado para establecer directivas de acceso condicional para Confianza cero mediante la integración de datos de Microsoft Defender para punto de conexión  u otros proveedores de seguridad móviles como origen de información para las directivas de cumplimiento de dispositivos y la implementación de directivas de acceso condicional basadas en dispositivos.

El riesgo del dispositivo influye directamente en qué recursos será accesible el usuario de ese dispositivo. La denegación de acceso a los recursos en función de determinados criterios es el tema principal de Confianza cero y Microsoft 365 Defender proporciona información necesaria para determinar los criterios de nivel de confianza. Por ejemplo, Microsoft 365 Defender puede proporcionar el nivel de versión de software de un dispositivo a través de la página Administración de amenazas y vulnerabilidades, mientras que las directivas de acceso condicional restringen los dispositivos que tienen versiones obsoletas o vulnerables.

La automatización es una parte fundamental de la implementación y el mantenimiento de un entorno de Confianza cero, a la vez que reduce el número de alertas que podrían dar lugar a eventos de respuesta a incidentes (IR). Los componentes de Microsoft 365 Defender se pueden automatizar, como [acciones de corrección](m365d-autoir.md) (conocidas como investigaciones de un incidente en el portal de Microsoft 365 Defender), acciones de notificación e incluso la creación de vales de soporte técnico, como en [ServiceNow](https://microsoft.service-now.com/sp/).

## <a name="step-2-determine-your-organizations-security-posture"></a>Paso 2. Determinación de la posición de seguridad de la organización

A continuación, las organizaciones pueden usar la [Puntuación de seguridad de Microsoft](microsoft-secure-score.md) en Microsoft 365 Defender para determinar su posición de seguridad actual y considerar recomendaciones sobre cómo mejorarla. Cuanto mayor sea la puntuación, más recomendaciones de seguridad y acciones de mejora han tomado la organización. Las recomendaciones de puntuación segura se pueden tomar en diferentes productos y permitir que las organizaciones aumenten sus puntuaciones aún más.

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Página Puntuación segura de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/first-incident-prepare/first-incident-secure-score.png":::

## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Paso 3. Evaluación de la exposición de vulnerabilidades de la organización

La prevención de incidentes puede ayudar a simplificar los esfuerzos de las operaciones de seguridad para centrarse en incidentes de seguridad críticos e importantes. Las vulnerabilidades de software suelen ser un punto de entrada evitable para los ataques que pueden provocar el robo de datos, la pérdida de datos o la interrupción de las operaciones empresariales. Si no hay ataques en marcha, las operaciones de seguridad deben esforzarse por lograr y mantener un nivel aceptable de [exposición a vulnerabilidades](../defender-endpoint/tvm-exposure-score.md) en su organización.

Para comprobar el progreso de la aplicación de revisiones de software, visite la página [Administración de amenazas y vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) de Defender para punto de conexión, a la que puede acceder desde Microsoft 365 Defender a través de la pestaña **Más recursos**.

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Página Amenazas y vulnerabilidades del portal de Microsoft 365 Defender" lightbox="../../media/first-incident-prepare/first-incident-vulnerability.png":::

## <a name="4-understand-emerging-threats"></a>4. Comprender las amenazas emergentes

Use [el análisis de amenazas](threat-analytics.md) en el portal de Microsoft 365 Defender para mantenerse al día con el panorama actual de amenazas de seguridad. Expertos investigadores de seguridad de Microsoft crean informes que describen las últimas ciberamenazas en detalle para que pueda comprender cómo podrían afectar a su suscripción, dispositivos y usuarios de Microsoft 365. Estos informes pueden incluir:

- Actores de amenazas activos y sus campañas
- Técnicas de ataque populares y nuevas
- Vulnerabilidades críticas
- Superficies de ataque comunes
- Malware frecuentes

Análisis de amenazas también examina la configuración y las alertas para determinar cómo está en riesgo y si hay alertas activas aplicables a un informe.

Puede implementar las recomendaciones de una amenaza emergente para reforzar la posición de seguridad y minimizar el área expuesta a ataques.

Anote su programación para comprobar periódicamente la sección [Análisis de amenazas](threat-analytics.md) del portal de Microsoft 365 Defender. Consulte [el ejemplo de operaciones de seguridad para Microsoft 365 Defender](incidents-overview.md#example-security-operations-for-microsoft-365-defender) para obtener más información.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo [evaluar y analizar incidentes](first-incident-analyze.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
