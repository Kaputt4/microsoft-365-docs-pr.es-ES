---
title: Paso 3. Planeamiento de Microsoft 365 Defender integración con el catálogo de servicios de SOC
description: Los conceptos básicos de la integración de Microsoft 365 Defender en el catálogo de servicios de operaciones de seguridad.
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
ms.openlocfilehash: 5db25bc333c09c284971b86c44a088a75fcaa92f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479652"
---
# <a name="step-3-plan-for-microsoft-365-defender-integration-with-your-soc-catalog-of-services"></a>Paso 3. Planeamiento de Microsoft 365 Defender integración con el catálogo de servicios de SOC

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Un centro de operaciones de seguridad (SOC) establecido debe tener un catálogo de servicios que pueda incluir:

- Intrusión & análisis de malware
- Atribución & ingeniería inversa
- Inteligencia sobre amenazas
- Análisis
- Investigación de búsqueda
- Análisis forense
- Respuesta a incidentes 
- Equipo de respuesta a incidentes de seguridad del equipo (CSIRT) (que se puede separar de SOC) 
- Pruebas de cumplimiento
- Supervisión de fraudes & amenazas internas
- Supervisión de eventos & incidentes de seguridad 
- Detección de vulnerabilidades
- Detección y respuesta extendidas (XDR)/Orquestación, automatización y respuesta de seguridad (SOAR)
- Suplantación de identidad (phishing)
- Prevención de pérdida de datos
- Supervisión de marca

Dado que Microsoft 365 Defender tecnologías abarcan varias funciones, el equipo de SOC deberá determinar qué roles y responsabilidades son más adecuados para administrar cada componente de Microsoft 365 Defender y alinearse con la función de servicio.

Los componentes de Microsoft 365 Defender son:

- **Microsoft Defender for Identity** (anteriormente Azure Advanced Threat Protection, también conocido como Azure ATP) es una solución de seguridad basada en la nube que usa Servicios de dominio de Active Directory  (AD DS) señales para identificar, detectar e investigar amenazas avanzadas, identidades en peligro y acciones internas malintencionadas dirigidas a las organizaciones.

- **Microsoft Defender para punto de conexión** es una solución holística de seguridad de puntos de conexión entregados en la nube para dispositivos que incluye la administración y evaluación de vulnerabilidades basada en riesgos, reducción de la superficie expuesta a ataques, protección de próxima generación basada en el comportamiento y con tecnología de nube, detección y respuesta de puntos de conexión (EDR), investigación y corrección automáticas, servicios de búsqueda administrados, API enriquecidas y unificado  administración de seguridad.

 - **Microsoft Defender para Office 365** es un servicio de filtrado de correo electrónico basado en la nube que ayuda a proteger a las organizaciones contra malware y virus desconocidos proporcionando una sólida protección de día cero e incluye características para proteger a las organizaciones de vínculos dañinos en tiempo real. También ofrece una lista completa de las características de investigación y búsqueda, respuesta y corrección, reconocimiento y entrenamiento, y características de posición segura.

- **Microsoft Defender for Cloud Apps** es un agente de seguridad de acceso a la nube (CASB) que admite varios modos de implementación, como la recopilación de registros, los conectores de API y el proxy inverso. Proporciona una visibilidad enriquecida, control sobre los viajes de datos y análisis sofisticados para identificar y combatir ciberamenazas en todos los servicios en la nube de Microsoft y de terceros.

Dado que Microsoft 365 Defender componentes y tecnologías abarcan varias funciones, el equipo de SOC deberá determinar qué roles y responsabilidades son más adecuados para administrar cada componente de Microsoft 365 Defender y alinearse con la función de servicio.

Para integrar las funcionalidades de Microsoft 365 Defender, deberá refinar los servicios soc. Para obtener más información sobre las funcionalidades de Microsoft 365 Defender, consulte los artículos siguientes:

- [¿Qué es Microsoft Defender para punto de conexión?](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)
- [¿Qué es Microsoft Defender for Identity?](/defender-for-identity/what-is)
- [¿Qué es Defender para Office 365?](/microsoft-365/security/defender/microsoft-365-defender)
- [¿Qué es Microsoft Defender for Cloud Apps?](/cloud-app-security/what-is-cloud-app-security)

## <a name="next-step"></a>Paso siguiente

[Paso 4. Definición de roles, responsabilidades y supervisión de Microsoft 365 Defender](integrate-microsoft-365-defender-secops-roles.md)
