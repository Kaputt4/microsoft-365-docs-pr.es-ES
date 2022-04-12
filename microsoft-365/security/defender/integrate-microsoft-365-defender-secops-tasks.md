---
title: Paso 6. Identificación de tareas de mantenimiento de SOC
description: Identifique las tareas de mantenimiento de SOC al integrar Microsoft 365 Defender en las operaciones de seguridad.
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
ms.openlocfilehash: 6b1ee22f8176d6f682eb9e9f2134cc27db91affd
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783631"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>Paso 6. Identificación de tareas de mantenimiento de SOC

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Estas son las tareas periódicas o según sea necesario para mantener el SOC para Microsoft 365 Defender.

|Actividad|Descripción|Cadencia|Equipo asignado|
|---|---|---|---|
|Colaboración de administración de servicios con SOC Teams|Administración de servicios periféricos como el seguimiento de recursos (CMDB), licencias de aplicaciones (nuevas licencias SaaS), compras de dispositivos (actualizaciones o renovación de implementaciones de dispositivos) y otros cambios Microsoft 365 en todo el inquilino (Intune, Microsoft 365 y otros) que pueden afectar a la implementación de productos Microsoft 365 Defender .|Semanalmente y según sea necesario|Ingeniería & SecOps|
|Actualización de campañas de prevención contra la suplantación de identidad (phishing) y la pérdida de datos|Incorpore el caso de uso de SOC y las lecciones aprendidas con una organización extendida (RR. HH., legal, aprendizaje, etc.).|Mensual y según sea necesario|Supervisión de SOC|
|Implementar scripts y servicios de automatización cuando corresponda|Descargue y pruebe scripts de automatización y archivos de configuración de sitios de Microsoft aprobados para mejorar las operaciones de Microsoft 365 Defender.|Semanalmente y según sea necesario|Ingeniería y SecOps|
|Administración de portales o licencias|Compruebe los anuncios y el Centro de Mensajes de Microsoft para conocer las necesidades de licencias o del portal de Microsoft 365 Defender en función de las actualizaciones de Microsoft y las nuevas características.|Semanal|Supervisión de SOC|
|Actualización de vales de escalación de SOC|Todos los equipos de SOC actualizan los vales de escalación (como sentinel, vales de ServiceNow) asignados a ellos.|Diario|Todos los equipos soc|
|Seguimiento de Microsoft 365 Defender actividad de corrección de vulnerabilidades & amenazas|Genere una actividad de corrección de TvM Secure Score e informe a los propietarios de recursos a través de un portal de intranet.|Diario|Supervisión|
|Generación de un informe de puntuación segura|El equipo de supervisión realiza un seguimiento e informa de las mejoras de puntuación segura.|SOC semanal|Supervisión|
|Ejecución del ejercicio de tabletop de IR|Pruebe los cuadernos de estrategias del equipo de SOC en el ejercicio de mesa.|(Según sea necesario)|Todos los equipos soc|

Integre estas tareas en los procesos de SOC actuales.

## <a name="next-steps"></a>Siguientes pasos

Debe revisar las guías a las que se hace referencia en este contenido y en la [biblioteca de Microsoft 365 Defender](/microsoft-365/security/defender) para determinar cómo se debe estructurar e integrar su propia implementación de Microsoft 365 Defender.
