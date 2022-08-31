---
title: Paso 6. Identificación de tareas de mantenimiento de SOC
description: Identifique las tareas de mantenimiento de SOC al integrar Microsoft 365 Defender en las operaciones de seguridad.
keywords: incidentes, alertas, investigación, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: b066b248444dbd897e7c560ec58622787c5fed9a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482436"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>Paso 6. Identificación de tareas de mantenimiento de SOC

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Estas son las tareas periódicas o según sea necesario para mantener el SOC para Microsoft 365 Defender.

|Actividad|Descripción|Cadencia|Equipo asignado|
|---|---|---|---|
|Colaboración de administración de servicios con SOC Teams|Administración de servicios periféricos, como el seguimiento de recursos (CMDB), licencias de aplicaciones (nuevas licencias SaaS), compras de dispositivos (actualizaciones o renovación de implementaciones de dispositivos) y otros cambios en todo el inquilino de Microsoft 365 (Intune, Microsoft 365 y otros) que pueden afectar a la implementación de Microsoft 365 Defender productos.|Semanalmente y según sea necesario|Ingeniería & SecOps|
|Actualización de campañas de prevención contra la suplantación de identidad (phishing) y la pérdida de datos|Incorpore el caso de uso de SOC y las lecciones aprendidas con una organización extendida (RR. HH., legal, aprendizaje, etc.).|Mensual y según sea necesario|Supervisión de SOC|
|Implementar scripts y servicios de automatización cuando corresponda|Descargue y pruebe scripts de automatización y archivos de configuración de sitios de Microsoft aprobados para mejorar las operaciones de Microsoft 365 Defender.|Semanalmente y según sea necesario|Ingeniería y SecOps|
|Administración de portales o licencias|Compruebe los anuncios y el Centro de Mensajes de Microsoft para conocer las necesidades de licencias o del portal de Microsoft 365 Defender en función de las actualizaciones de Microsoft y las nuevas características.|Semanal|Supervisión de SOC|
|Actualización de vales de escalación de SOC|Todos los equipos de SOC actualizan los vales de escalación (como sentinel, vales de ServiceNow) asignados a ellos.|Diario|Todos los equipos soc|
|Seguimiento de la actividad de corrección de Administración de vulnerabilidades de Microsoft Defender (MDVM)|Genere la actividad de corrección mdvm secure score e informe a los propietarios de recursos a través de un portal de intranet.|Diario|Supervisión|
|Generación de un informe de puntuación segura|El equipo de supervisión realiza un seguimiento e informa de las mejoras de puntuación segura.|SOC semanal|Supervisión|
|Ejecución del ejercicio de tabletop de IR|Pruebe los cuadernos de estrategias del equipo de SOC en el ejercicio de mesa.|(Según sea necesario)|Todos los equipos soc|

Integre estas tareas en los procesos de SOC actuales.

## <a name="next-steps"></a>Pasos siguientes

Debe revisar las guías a las que se hace referencia en este contenido y en la [biblioteca de Microsoft 365 Defender](/microsoft-365/security/defender) para determinar cómo se debe estructurar e integrar su propia implementación de Microsoft 365 Defender.
