---
title: Cambiar de la protección de puntos de conexión que no son de Microsoft a Microsoft Defender para el extremo
description: Cambia a Microsoft Defender para Endpoint, que incluye Antivirus de Microsoft Defender para la solución de protección de puntos de conexión.
keywords: migración, Windows Defender, protección avanzada de puntos de conexión, antivirus, antimalware, modo pasivo, modo activo
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
- m365initiative-defender-endpoint
ms.topic: overview
ms.custom: migrationguides
ms.date: 11/29/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: eb0971c6f5b8fd8bf37f3d33cb65cff8d331e0d0
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62245308"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Cambiar de la protección de puntos de conexión que no son de Microsoft a Microsoft Defender para el extremo

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804) Si está considerando cambiar de una solución de protección de puntos de conexión que no sea de Microsoft a [Microsoft Defender para](microsoft-defender-endpoint.md) endpoint (Defender para endpoint) o está en la fase de planeación, use este artículo como guía. En este artículo se describe el proceso general de pasar a Defender para endpoint.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Cambie la solución de protección de puntos de conexión a Defender for Endpoint.":::

Al cambiar a Defender for Endpoint, comienza con la protección contra antivirus o antimalware que no es de Microsoft en modo activo. A continuación, configuras Antivirus de Microsoft Defender modo pasivo e incorporas tus dispositivos a Defender para endpoint. A continuación, configure las características de protección de puntos de conexión, establezca Antivirus de Microsoft Defender en modo activo y compruebe que todo funciona correctamente. Por último, se quita la solución que no es de Microsoft.

## <a name="the-migration-process"></a>Proceso de migración

El proceso de migración a Defender for Endpoint se puede dividir en tres fases, como se describe en la tabla siguiente:

![Proceso de migración de MDE.](images/phase-diagrams/migration-phases.png)

<br/><br/>

|Fase|Descripción|
|--|--|
|[Preparar la migración](switch-to-mde-phase-1.md)|Durante [la fase **de** preparación:](switch-to-mde-phase-1.md) <br/>1. Actualice los dispositivos de su organización.<br/>2. Obtener Defender para endpoint.<br/>3. Planee roles y permisos y conceda acceso al portal Microsoft 365 Defender web.<br/>4. Configure el proxy del dispositivo y la configuración de Internet para habilitar la comunicación entre los dispositivos de la organización y Defender para endpoint. |
|[Configurar Defender para endpoint](switch-to-mde-phase-2.md)|Durante [la fase **de** instalación:](switch-to-mde-phase-2.md) <br/>1. Habilite o vuelva a instalar Antivirus de Microsoft Defender y estabilite en modo pasivo.<br/>2. Configure Defender for Endpoint.<br/>3. Agregue Defender for Endpoint a la lista de exclusión de la solución existente.<br/>4. Agregue la solución existente a la lista de exclusión para Antivirus de Microsoft Defender.<br/>5. Configure los grupos de dispositivos, las colecciones y las unidades organizativas.<br/>6. Configure las directivas antimalware y la configuración de protección en tiempo real.|
|[Incorporación a Defender para endpoint](switch-to-mde-phase-3.md)|Durante [la fase de **incorporación**](switch-to-mde-phase-3.md): <br/>1. Incorpore los dispositivos a Defender para endpoint.<br/>2. Ejecute una prueba de detección.<br/>3. Confirme que Antivirus de Microsoft Defender se está ejecutando en modo pasivo.<br/>4. Obtener actualizaciones para Antivirus de Microsoft Defender.<br/>5. Desinstale la solución de protección de extremo existente.<br/>6. Asegúrese de que Defender for Endpoint funciona correctamente.|

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>¿Qué se incluye en Microsoft Defender para endpoint?

En esta guía de [](microsoft-defender-antivirus-in-windows-10.md) migración, nos centramos en la protección de próxima generación y las [detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) como punto de partida para pasar a Defender for Endpoint. Sin embargo, Defender for Endpoint incluye mucho más que antivirus y protección de puntos de conexión. Defender for Endpoint es una plataforma unificada para la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta. En la tabla siguiente se resumen las características y capacidades de Defender para endpoint.

<br/><br/>

|Característica/funcionalidad|Descripción|
|---|---|
|[Administración de vulnerabilidades y amenazas](next-gen-threat-and-vuln-mgt.md)|Las & administración de vulnerabilidades de amenazas ayudan a identificar, evaluar y corregir puntos débiles en los puntos de conexión (como dispositivos).|
|[Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)|Las reglas de reducción de superficie de ataque ayudan a proteger los dispositivos y aplicaciones de la organización de ciberamenazas y ataques.|
|[Protección de última generación](microsoft-defender-antivirus-in-windows-10.md)|La protección de última generación Antivirus de Microsoft Defender ayuda a bloquear amenazas y malware.|
|[EDR](overview-endpoint-detection-response.md)|Las capacidades de detección y respuesta de puntos de conexión detectan, investigan y responden a intentos de intrusión e infracciones activas.|
|[Búsqueda avanzada de amenazas](advanced-hunting-overview.md)|Las capacidades avanzadas de búsqueda permiten al equipo de operaciones de seguridad localizar indicadores y entidades de amenazas conocidas o potenciales.|
|[Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)|Las capacidades de bloqueo y contención del comportamiento ayudan a identificar y detener las amenazas, en función de sus comportamientos y de los árboles de proceso incluso cuando la amenaza ha comenzado a ejecutarse.|
|[Investigación y corrección automatizadas](automated-investigations.md)|Las capacidades automatizadas de investigación y respuesta examinan las alertas y toman medidas de corrección inmediatas para resolver infracciones.|
|[Servicio de búsqueda de](microsoft-threat-experts.md) amenazas (Expertos en amenazas de Microsoft)|Los servicios de búsqueda de amenazas proporcionan a los equipos de operaciones de seguridad supervisión y análisis de nivel de expertos, y para ayudar a garantizar que no se pierden las amenazas críticas.|

**¿Desea obtener más información? Consulte [Defender for Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Paso siguiente

- Continúe con [Prepare for your migration](switch-to-mde-phase-1.md).
