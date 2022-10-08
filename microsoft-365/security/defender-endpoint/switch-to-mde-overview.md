---
title: Haga que el cambio de endpoint protection que no es de Microsoft a Microsoft Defender para punto de conexión
description: Realice el cambio a Microsoft Defender para punto de conexión, que incluye Microsoft Defender Antivirus para la solución de endpoint protection.
keywords: migración, Windows Defender, protección avanzada de puntos de conexión, antivirus, antimalware, modo pasivo, modo activo
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-migratetomdatp
- m365solution-overview
- m365initiative-defender-endpoint
- highpri
- tier1
ms.topic: overview
ms.custom: migrationguides
ms.date: 09/29/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: c81e458d57b4e8ccc67d409a1f11e66b201d8938
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222944"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Haga que el cambio de endpoint protection que no es de Microsoft a Microsoft Defender para punto de conexión

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Si está pensando en cambiar de una solución de protección de puntos de conexión que no es de Microsoft a [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md) (Defender para punto de conexión), o está en la fase de planeación, use este artículo como guía. En este artículo se describe el proceso general de traslado a Defender para punto de conexión.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Proceso de migración para cambiar la solución de Endpoint Protection a Defender para punto de conexión" lightbox="images/nonms-mde-migration.png":::

Al cambiar a Defender para punto de conexión, comienza con la protección antivirus o antimalware que no es de Microsoft en modo activo. A continuación, configure Microsoft Defender Antivirus en modo pasivo e incorpore los dispositivos a Defender para punto de conexión. A continuación, configure las características de Endpoint Protection, establezca Microsoft Defender Antivirus en modo activo y compruebe que todo funciona correctamente. Por último, se quita la solución que no es de Microsoft.

## <a name="the-migration-process"></a>El proceso de migración

El proceso de migración a Defender para punto de conexión se puede dividir en tres fases, como se describe en la tabla siguiente:

:::image type="content" source="images/phase-diagrams/migration-phases.png" alt-text="Proceso de migración de MDE" lightbox="images/phase-diagrams/migration-phases.png":::


<br/><br/>

|Fase|Descripción|
|--|--|
|[Preparación para la migración](switch-to-mde-phase-1.md)|Durante [la fase **de preparación**](switch-to-mde-phase-1.md): <br/>1. Actualice los dispositivos de la organización.<br/>2. Obtener Defender para punto de conexión.<br/>3. Planear roles y permisos, y conceder acceso al portal de Microsoft 365 Defender.<br/>4. Configure el proxy del dispositivo y la configuración de Internet para habilitar la comunicación entre los dispositivos de la organización y Defender para punto de conexión. |
|[Configuración de Defender para punto de conexión](switch-to-mde-phase-2.md)|Durante [la fase **de instalación**](switch-to-mde-phase-2.md): <br/>1. Habilite o vuelva a instalar Microsoft Defender Antivirus y establézcalo en modo pasivo.<br/>2. Configurar Defender para punto de conexión.<br/>3. Agregue Defender para punto de conexión a la lista de exclusión de la solución existente.<br/>4. Agregue la solución existente a la lista de exclusión de Microsoft Defender Antivirus.<br/>5. Configure los grupos de dispositivos, las colecciones y las unidades organizativas.|
|[Incorporación a Defender para punto de conexión](switch-to-mde-phase-3.md)|Durante [la fase **de incorporación**](switch-to-mde-phase-3.md): <br/>1. Incorpore los dispositivos a Defender para punto de conexión.<br/>2. Ejecute una prueba de detección.<br/>3. Confirme que Microsoft Defender Antivirus se ejecuta en modo pasivo.<br/>4. Obtener actualizaciones para Microsoft Defender Antivirus.<br/>5. Desinstale la solución de endpoint protection existente.<br/>6. Asegúrese de que Defender para punto de conexión funciona correctamente.|

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>¿Qué se incluye en Microsoft Defender para punto de conexión?

En esta guía de migración, nos centramos en la [protección de última generación](microsoft-defender-antivirus-in-windows-10.md) y en las funcionalidades [de detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) como punto de partida para pasar a Defender para punto de conexión. Sin embargo, Defender para punto de conexión incluye mucho más que antivirus y endpoint protection. Defender for Endpoint es una plataforma unificada para la protección preventiva, la detección posterior a la vulneración, la investigación automatizada y la respuesta. En la tabla siguiente se resumen las características y funcionalidades de Defender para punto de conexión.

<br/><br/>

|Característica o funcionalidad|Descripción|
|---|---|
|[Administración de vulnerabilidades de Microsoft Defender](next-gen-threat-and-vuln-mgt.md)|Las funcionalidades de Administración de vulnerabilidades de Defender ayudan a identificar, evaluar y corregir las debilidades en los puntos de conexión (como los dispositivos).|
|[Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)|Las reglas de reducción de superficie expuesta a ataques ayudan a proteger los dispositivos y las aplicaciones de su organización frente a ciberataques y ataques.|
|[Protección de última generación](microsoft-defender-antivirus-in-windows-10.md)|La protección de última generación incluye Microsoft Defender Antivirus para ayudar a bloquear las amenazas y el malware.|
|[EDR](overview-endpoint-detection-response.md)|Las funcionalidades de detección y respuesta de puntos de conexión detectan, investigan y responden a intentos de intrusiones y infracciones activas.|
|[Búsqueda avanzada de amenazas](advanced-hunting-overview.md)|Las funcionalidades avanzadas de búsqueda permiten al equipo de operaciones de seguridad localizar indicadores y entidades de amenazas conocidas o potenciales.|
|[Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)|Las funcionalidades de bloqueo y contención del comportamiento ayudan a identificar y detener amenazas, en función de sus comportamientos y de los árboles de proceso, incluso cuando la amenaza ha comenzado a ejecutarse.|
|[Investigación y corrección automatizadas](automated-investigations.md)|Las funcionalidades automatizadas de investigación y respuesta examinan las alertas y toman medidas de corrección inmediatas para resolver las infracciones.|
|[Servicio de búsqueda de amenazas](microsoft-threat-experts.md) (Expertos en amenazas de Microsoft)|Los servicios de búsqueda de amenazas proporcionan a los equipos de operaciones de seguridad supervisión y análisis de nivel experto, y para ayudar a garantizar que no se pierdan amenazas críticas.|

**¿Desea obtener más información? Consulte [Defender para punto de conexión](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Paso siguiente

- Continúe con [Preparación para la migración](switch-to-mde-phase-1.md).
