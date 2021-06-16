---
title: Cambiar de la protección de puntos de conexión que no son de Microsoft a Microsoft Defender para el extremo
description: Realice el cambio a Microsoft Defender para endpoint. Lea este artículo para obtener información general.
keywords: migración, protección avanzada de puntos de conexión de Windows Defender, para Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2953103cb3812103740f98a6db5b8f4d369731e3
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930312"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Cambiar de la protección de puntos de conexión que no son de Microsoft a Microsoft Defender para el extremo

Si está pensando en cambiar de una solución de protección de puntos de conexión que no es de Microsoft a [Microsoft Defender para](microsoft-defender-endpoint.md) Endpoint (Defender para endpoint), está en el lugar correcto. Use este artículo como guía.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Información general sobre la migración a Defender for Endpoint":::

Cuando cambias a Defender for Endpoint, comienzas con la solución que no es microsoft funcionando en modo activo. Después, configuras Defender para Endpoint en modo pasivo e incorporas tus dispositivos a Defender para endpoint. A continuación, establece Defender para Endpoint en modo activo. Por último, se quita la solución que no es de Microsoft.

## <a name="the-migration-process"></a>Proceso de migración

El proceso de migración a Defender for Endpoint se puede dividir en tres fases, como se describe en la tabla siguiente:

![Fases de migración: preparar, configurar, incorporar](images/phase-diagrams/migration-phases.png)

|Fase |Descripción |
|--|--|
|[Preparar la migración](switch-to-microsoft-defender-prepare.md) |Durante [la fase **de** preparación:](switch-to-microsoft-defender-prepare.md) <p>1. Actualice los dispositivos de su organización. <p>2. Obtener Defender para endpoint. <p>3. Planee sus roles y permisos y conceda acceso a la Centro de seguridad de Microsoft Defender. <p>4. Configure el proxy del dispositivo y la configuración de Internet para habilitar la comunicación entre los dispositivos de la organización y Defender para endpoint. |
|[Configurar Defender para endpoint](switch-to-microsoft-defender-setup.md) |Durante [la fase **de** instalación:](switch-to-microsoft-defender-setup.md) <p>1. Habilite o vuelva a instalar Antivirus de Microsoft Defender. <p>2. Configure Defender for Endpoint. <p>3. Agregue Defender for Endpoint a la lista de exclusión de la solución existente. <p>4. Agregue la solución existente a la lista de exclusión para Antivirus de Microsoft Defender. <p>5. Configure los grupos de dispositivos, las colecciones y las unidades organizativas. <p>6. Configure las directivas antimalware y la configuración de protección en tiempo real.|
|[Incorporación a Defender para endpoint](switch-to-microsoft-defender-onboard.md) |Durante [la fase de **incorporación**](switch-to-microsoft-defender-onboard.md): <p>1. Incorpore los dispositivos a Defender para endpoint. <p>2. Ejecute una prueba de detección. <p>3. Confirme que Antivirus de Microsoft Defender se está ejecutando en modo pasivo. <p>4. Obtener actualizaciones para Antivirus de Microsoft Defender. <p>5. Desinstale la solución de protección de extremo existente. <p>6. Asegúrese de que Defender for Endpoint funciona correctamente. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>¿Qué se incluye en Microsoft Defender para endpoint?

En esta guía de [](microsoft-defender-antivirus-in-windows-10.md) migración, nos centramos en la protección de próxima generación y las [detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) como punto de partida para pasar a Defender for Endpoint. Sin embargo, Defender for Endpoint incluye mucho más que antivirus y protección de puntos de conexión. Defender for Endpoint es una plataforma unificada para la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta. En la tabla siguiente se resumen las características y capacidades de Defender para endpoint. 

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

**¿Desea obtener más información? Consulte [Defender for Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Paso siguiente

- Continúe con [Prepare for your migration](switch-to-microsoft-defender-prepare.md).
