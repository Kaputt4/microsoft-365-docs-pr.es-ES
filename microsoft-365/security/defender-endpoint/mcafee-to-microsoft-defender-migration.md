---
title: Migrar de McAfee a Microsoft Defender para endpoint
description: Realice el cambio de McAfee a Microsoft Defender para Endpoint. Lea este artículo para obtener información general.
keywords: migración, Microsoft Defender para Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5bbcf885ec160204916507aee60398aee35e470b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538056"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Migrar de McAfee a Microsoft Defender para endpoint

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Si tiene previsto cambiar de McAfee Endpoint Security (McAfee) a [Microsoft Defender para Endpoint](microsoft-defender-endpoint.md) (Microsoft Defender para Endpoint), está en el lugar correcto. Use este artículo como guía.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Información general sobre la migración de McAfee a Defender for Endpoint":::

Al cambiar de McAfee a Defender para endpoint, empieza por la solución de McAfee en modo activo, configura Defender para endpoint en modo pasivo, se incorpora a Defender para endpoint y, a continuación, establece Defender for Endpoint en modo activo y quita McAfee.

## <a name="the-migration-process"></a>Proceso de migración

Al cambiar de McAfee a Microsoft Defender para Endpoint, sigue un proceso que se puede dividir en tres fases: Preparar, Configurar e Incorporar. 

![Fases de migración: preparar la instalación integrada](images/phase-diagrams/migration-phases.png)

|Fase |Descripción |
|--|--|
|[Preparar la migración](mcafee-to-microsoft-defender-prepare.md) |Durante la [**fase de**](mcafee-to-microsoft-defender-prepare.md) preparación, actualiza los dispositivos de la organización, obtiene Microsoft Defender para endpoint, planea sus roles y permisos y concede acceso a la Centro de seguridad de Microsoft Defender. También configuras el proxy de dispositivo y la configuración de Internet para habilitar la comunicación entre los dispositivos de la organización y Microsoft Defender para endpoint. |
|[Configurar Microsoft Defender para endpoint](mcafee-to-microsoft-defender-setup.md) |Durante la [**fase de**](mcafee-to-microsoft-defender-setup.md) configuración, se habilita Antivirus de Microsoft Defender y se establece en modo pasivo. También se configuran las opciones & exclusiones para Antivirus de Microsoft Defender y la solución de protección de puntos de conexión existente. A continuación, creas los grupos de dispositivos, las colecciones y las unidades organizativas. Por último, se configuran las directivas antimalware y la configuración de protección en tiempo real.|
|[Incorporación a Microsoft Defender para endpoint](mcafee-to-microsoft-defender-onboard.md) |Durante la [**fase**](mcafee-to-microsoft-defender-onboard.md) de incorporación, incorporas los dispositivos a Microsoft Defender para endpoint, confirmas que Antivirus de Microsoft Defender se ejecuta en modo pasivo y compruebas que los puntos de conexión se comunican con Defender para endpoint. A continuación, desinstale McAfee y asegúrese de que Defender for Endpoint funciona correctamente. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>¿Qué se incluye en Microsoft Defender para endpoint?

En esta guía de [](microsoft-defender-antivirus-in-windows-10.md) migración, nos centramos en la protección de próxima generación y las [detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) como punto de partida para pasar a Microsoft Defender para endpoint. Sin embargo, Microsoft Defender para endpoint incluye mucho más que antivirus y protección de puntos de conexión. Microsoft Defender para punto de conexión es una plataforma unificada para la protección preventiva, la detección posterior a la vulneración y la respuesta e investigación automatizadas. En la tabla siguiente se resumen las características y capacidades de Microsoft Defender para endpoint. 

| Característica/funcionalidad | Descripción |
|---|---|
| [Administración de vulnerabilidades y amenazas](next-gen-threat-and-vuln-mgt.md) | Las & administración de vulnerabilidades de amenazas ayudan a identificar, evaluar y corregir puntos débiles en los puntos de conexión (como dispositivos). |
| [Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md) | Las reglas de reducción de superficie de ataque ayudan a proteger los dispositivos y aplicaciones de la organización de ciberamenazas y ataques. |
| [Protección de última generación](microsoft-defender-antivirus-in-windows-10.md) | La protección de última generación Antivirus de Microsoft Defender ayuda a bloquear amenazas y malware. |
| [EDR](overview-endpoint-detection-response.md) | Las capacidades de detección y respuesta de puntos de conexión detectan, investigan y responden a intentos de intrusión e infracciones activas.  |
| [Búsqueda avanzada de amenazas](advanced-hunting-overview.md) | Las capacidades avanzadas de búsqueda permiten al equipo de operaciones de seguridad localizar indicadores y entidades de amenazas conocidas o potenciales. |
| [Bloqueo y contención de comportamientos](behavioral-blocking-containment.md) | Las capacidades de bloqueo y contención del comportamiento ayudan a identificar y detener las amenazas, en función de sus comportamientos y de los árboles de proceso incluso cuando la amenaza ha comenzado a ejecutarse. |
| [Investigación y corrección automatizadas](automated-investigations.md) | Las capacidades automatizadas de investigación y respuesta examinan las alertas y toman medidas de corrección inmediatas para resolver infracciones. |
| [Servicio de búsqueda de](microsoft-threat-experts.md) amenazas (Expertos en amenazas de Microsoft) | Los servicios de búsqueda de amenazas proporcionan a los equipos de operaciones de seguridad supervisión y análisis de nivel de expertos, y para ayudar a garantizar que no se pierden las amenazas críticas. |

**¿Desea obtener más información? Consulta [Microsoft Defender para Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Paso siguiente

- Continúe con [Prepare for your migration](mcafee-to-microsoft-defender-prepare.md).
