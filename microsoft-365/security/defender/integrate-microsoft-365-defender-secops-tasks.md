---
title: Paso 6. Identificar tareas de mantenimiento soc
description: Identifique las tareas de mantenimiento de SOC al integrar Microsoft 365 Defender en las operaciones de seguridad.
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
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d56a062a54439103fc8beca17c925602e374edda
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172012"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>Paso 6. Identificar tareas de mantenimiento soc

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Estas son las tareas periódicas o según sea necesario para mantener el SOC para Microsoft 365 Defender.

| Actividad  | Descripción | Cadencia | Equipo asignado |
|:-------|:-----|:-------|:-------|
| Colaboración de administración de servicios con SOC Teams   | Administración de servicios periféricos como seguimiento de activos (CMDB), licencias de aplicaciones (nuevas licencias SaaS), compras de dispositivos (actualizaciones o renovar implementaciones de dispositivos) y otros cambios Microsoft 365 en todo el espacio empresarial (Intune, Microsoft 365 y otros) que pueden afectar a la implementación de productos Microsoft 365 Defender. | Semanalmente y según sea necesario   | Ingeniería & SecOps | 
| Actualizar campañas de prevención contra la suplantación de identidad (phishing) y pérdida de datos | Incorporar casos de uso de SOC y lecciones aprendidas con la organización extendida (recursos humanos, legales, formación y otros).  | Mensualmente y según sea necesario | Supervisión de SOC |
| Implementar scripts y servicios de automatización cuando corresponda | Descargue y pruebe los scripts de automatización y los archivos de configuración de los sitios de Microsoft aprobados para mejorar Microsoft 365 Defender operaciones. | Semanalmente y según sea necesario | Ingeniería y SecOps | 
| Administración de portales o licencias | Compruebe los anuncios y el Centro de Mensajes de Microsoft para obtener Microsoft 365 Defender de licencias o portal basado en las actualizaciones de Microsoft y las nuevas características. | Semanal | Supervisión de SOC| 
| Actualizar vales de escalamiento SOC | Todos los equipos SOC actualizan los vales de escalamiento (como los vales de Sentinel, ServiceNow) asignados a ellos. | Diario | Todos los equipos soc | 
| Realizar Microsoft 365 Defender actividad de corrección & vulnerabilidades | Generar actividad de corrección de puntuación segura de TvM e informar a los propietarios de activos a través de un portal de intranet. | Diario | Supervisión | 
| Generar informe de puntuación segura | El equipo de supervisión realiza un seguimiento e informa de mejoras de puntuación segura. | SOC semanal | Supervisión | 
| Ejecutar ejercicio de tabla IR | Prueba los libros de juego de equipo de SOC en el ejercicio de tabla. | (Según sea necesario) | Todos los equipos soc | 
|||||

Integre estas tareas en los procesos SOC actuales.

## <a name="next-steps"></a>Pasos siguientes

Debe revisar las guías a las que se hace referencia en este contenido y en la biblioteca [de Microsoft 365 Defender](/microsoft-365/security/defender) para determinar cómo se debe estructurar e integrar su propia implementación de Microsoft 365 Defender.
