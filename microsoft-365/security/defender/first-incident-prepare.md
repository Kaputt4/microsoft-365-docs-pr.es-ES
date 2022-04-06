---
title: Preparar la posición de seguridad para el primer incidente
description: Configure la posición Microsoft 365 seguridad del inquilino para su primer incidente en Microsoft 365 Defender.
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
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 92b7efdad61a4738310d5fb469400033f78363a8
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64570159"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Preparar la posición de seguridad para el primer incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Prepararse para el tratamiento de incidentes implica configurar la protección suficiente de la red de una organización frente a distintos tipos de incidentes de seguridad. Para reducir el riesgo de incidentes de seguridad, el Instituto Nacional de Estándares y Tecnología (NIST) recomienda varias prácticas de seguridad, como evaluaciones de riesgos, protección de la seguridad de host, configuración de redes de forma segura y prevención de malware. 

Microsoft 365 Defender puede ayudar a abordar varios aspectos de la prevención de incidentes: 

- Implementar un [marco Confianza cero](/security/zero-trust/) de trabajo
- Determinación de la posición de seguridad mediante la asignación de una puntuación con [puntuación segura de Microsoft](microsoft-secure-score.md)
- Prevención de amenazas mediante evaluaciones de vulnerabilidad en [Administración de amenazas y vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Descripción de las amenazas de seguridad más recientes para que pueda prepararse para ellas con análisis [de amenazas](threat-analytics.md)

## <a name="step-1-implement-zero-trust"></a>Paso 1. Implementar Confianza cero

[Confianza cero](/security/zero-trust/) es una filosofía de seguridad integrada y una estrategia integral que tiene en cuenta la naturaleza compleja de cualquier entorno moderno, incluidos los trabajadores móviles y los usuarios, dispositivos, aplicaciones y datos, dondequiera que estén ubicados. Al proporcionar un único panel de cristal para administrar todas las detecciones de forma coherente, Microsoft 365 Defender puede facilitar a su equipo de operaciones de seguridad implementar los [principios](/security/zero-trust/#guiding-principles-of-zero-trust) de guía de Confianza cero. 

Los componentes de Microsoft 365 Defender pueden mostrar infracciones de reglas que se han implementado para establecer directivas de acceso condicional para Confianza cero integrando datos de Microsoft Defender para punto de conexión  u otros proveedores de seguridad móvil como origen de información para las directivas de cumplimiento de dispositivos y la implementación de directivas de acceso condicional basadas en dispositivos. 

El riesgo del dispositivo influye directamente en los recursos a los que podrá acceder el usuario de ese dispositivo. La denegación de acceso a los recursos según determinados criterios es el tema principal de Confianza cero y Microsoft 365 Defender proporciona la información necesaria para determinar los criterios de nivel de confianza. Por ejemplo, Microsoft 365 Defender proporcionar el nivel de versión de software de un dispositivo a través de la página Administración de amenazas y vulnerabilidades, mientras que las directivas de acceso condicional restringen los dispositivos que tienen versiones obsoletas o vulnerables.

La automatización es una parte fundamental de la implementación y el mantenimiento de un entorno Confianza cero, a la vez que reduce el número de alertas que potencialmente llevarían a eventos de respuesta a incidentes (IR). Los componentes de Microsoft 365 Defender pueden automatizarse, como acciones de [corrección (](m365d-autoir.md)conocidas como investigaciones de un incidente en el portal de Microsoft 365 Defender), acciones de notificación e incluso la creación de vales de soporte técnico, como [en ServiceNow](https://microsoft.service-now.com/sp/).

## <a name="step-2-determine-your-organizations-security-posture"></a>Paso 2. Determinar la posición de seguridad de la organización

A continuación, las organizaciones pueden usar la puntuación segura de [Microsoft](microsoft-secure-score.md) en Microsoft 365 Defender para determinar la posición de seguridad actual y considerar recomendaciones sobre cómo mejorarla. Cuanto mayor sea la puntuación, más recomendaciones de seguridad y acciones de mejora han sido tomadas por la organización. Las recomendaciones de puntuación segura se pueden tomar en diferentes productos y permitir que las organizaciones eleven sus puntuaciones incluso más alto. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Página Puntuación segura de Microsoft en el portal de Microsoft 365 Defender seguridad" lightbox="../../media/first-incident-prepare/first-incident-secure-score.png":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Paso 3. Evaluar la exposición a vulnerabilidades de su organización

La prevención de incidentes puede ayudar a simplificar los esfuerzos de las operaciones de seguridad para centrarse en los incidentes de seguridad importantes y críticos en curso. Las vulnerabilidades de software suelen ser un punto de entrada evitable para ataques que pueden provocar el robo de datos, la pérdida de datos o la interrupción de las operaciones empresariales. Si no hay ataques en curso, las operaciones de seguridad deben esforzarse por lograr y mantener un nivel aceptable de exposición [a la vulnerabilidad](../defender-endpoint/tvm-exposure-score.md) en su organización.

Para comprobar el progreso de la revisión de software [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md), visita la página Administración de amenazas y vulnerabilidades de Defender for Endpoint, a la que puedes acceder desde Microsoft 365 Defender a través de la pestaña **Más recursos.**

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="La página Amenaza y vulnerabilidad del portal de Microsoft 365 Defender web" lightbox="../../media/first-incident-prepare/first-incident-vulnerability.png"::: 
 
## <a name="4-understand-emerging-threats"></a>4. Comprender las amenazas emergentes

Use [el análisis de](threat-analytics.md) amenazas en el portal de Microsoft 365 Defender para mantenerse al día con el panorama actual de amenazas de seguridad. Los expertos investigadores de seguridad de Microsoft crean informes que describen en detalle las últimas amenazas cibernéticas para que pueda comprender cómo pueden afectar a su suscripción Microsoft 365, dispositivos y usuarios. Estos informes pueden incluir:

- Actores de amenazas activas y sus campañas
- Técnicas de ataque populares y nuevas
- Vulnerabilidades críticas
- Superficies de ataque comunes
- Malware frecuentes

El análisis de amenazas también examina la configuración y las alertas para determinar el riesgo que tiene y si hay alertas activas aplicables a un informe.

Puedes implementar las recomendaciones de una amenaza emergente para reforzar tu posición de seguridad y minimizar la superficie de ataque.

Haga tiempo en su programación para comprobar periódicamente la sección [Análisis de](threat-analytics.md) amenazas del portal de Microsoft 365 Defender web. Vea el [ejemplo de operaciones de seguridad Microsoft 365 Defender](incidents-overview.md#example-security-operations-for-microsoft-365-defender) para obtener más información.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre [cómo triage and analyze incidents](first-incident-analyze.md).

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
