---
title: Paso 3. Plan for Microsoft 365 Defender integration with your SOC catalog of services
description: Los conceptos básicos de la integración Microsoft 365 Defender en el catálogo de servicios de operaciones de seguridad.
keywords: incidentes, alertas, investigar, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
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
ms.openlocfilehash: 45497f74db9c68959d4b23e013c6ea483e86378a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323967"
---
# <a name="step-3-plan-for-microsoft-365-defender-integration-with-your-soc-catalog-of-services"></a>Paso 3. Plan for Microsoft 365 Defender integration with your SOC catalog of services

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Un Centro de operaciones de seguridad (SOC) establecido debe tener un catálogo de servicios que pueda incluir:

- Análisis & malware de intrusiones
- Atribución & ingeniería inversa
- Inteligencia de amenazas
- Análisis
- Investigación de la búsqueda
- Análisis forense
- Respuesta a incidentes 
- Equipo de respuesta a incidentes de seguridad del equipo (CSIRT) (que se puede segregar de SOC) 
- Pruebas de cumplimiento
- Supervisión de la & de amenazas insider
- Supervisión de eventos & incidentes de seguridad 
- Detección de vulnerabilidades
- Detección extendida y respuesta (XDR)/Orquestación de seguridad, automatización y respuesta (SOAR)
- Suplantación de identidad (phishing)
- Prevención de pérdida de datos
- Supervisión de marca

Dado que Microsoft 365 Defender tecnologías abarcan varias funciones, el equipo de SOC tendrá que determinar qué roles y responsabilidades son más adecuados para administrar cada componente de Microsoft 365 Defender y alinearse con la función de servicio.

Los componentes de Microsoft 365 Defender son:

- **Microsoft Defender for Identity** (anteriormente Azure Advanced Threat Protection, también conocido como Azure ATP) es una solución de seguridad basada en la nube que usa señales de Servicios de dominio de Active Directory (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones malintencionadas dirigidas a organizaciones.

- **Microsoft Defender para** endpoint es una solución de seguridad de puntos de conexión holística y entregada en la nube para dispositivos que incluye administración de vulnerabilidades y evaluación basada en riesgos, reducción de superficie de ataque, protección de próxima generación basada en el comportamiento y con tecnología en la nube, detección y respuesta de puntos de conexión (EDR), investigación y corrección automáticas, servicios de búsqueda administrados, API enriquecciones y administración de seguridad unificada.

 - **Microsoft Defender para Office 365** es un servicio de filtrado de correo electrónico basado en la nube que ayuda a proteger a las organizaciones contra malware y virus desconocidos al proporcionar una protección sólida de día cero e incluye características para proteger a las organizaciones de vínculos dañinos en tiempo real. También ofrece una lista completa de investigación y búsqueda, respuesta y corrección, sensibilización y formación, y características de postura segura.

- **Microsoft Defender para Aplicaciones en** la nube es un agente de seguridad de acceso a la nube (CASB) que admite varios modos de implementación, como la recopilación de registros, los conectores de API y el proxy inverso. Proporciona una amplia visibilidad, control sobre los viajes de datos y análisis sofisticados para identificar y combatir ciberamenazas en todos los servicios en la nube de Microsoft y de terceros.

Dado que Microsoft 365 Defender componentes y tecnologías abarcan varias funciones, el equipo de SOC tendrá que determinar qué roles y responsabilidades son más adecuados para administrar cada componente de Microsoft 365 Defender y alinearse con la función de servicio.

Para integrar las capacidades de Microsoft 365 Defender, deberá refinar los servicios SOC. Para obtener más información acerca de las funcionalidades de Microsoft 365 Defender, vea los siguientes artículos:

- [¿Qué es Microsoft Defender para punto de conexión?](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)
- [¿Qué es Microsoft Defender for Identity?](/defender-for-identity/what-is)
- [¿Qué es Defender para Office 365?](/office-365-security/defender-for-office-365)
- [¿Qué es Microsoft Defender for Cloud Apps?](/cloud-app-security/what-is-cloud-app-security)

## <a name="next-step"></a>Paso siguiente

[Paso 4. Definir Microsoft 365 Defender roles, responsabilidades y supervisión](integrate-microsoft-365-defender-secops-roles.md)
