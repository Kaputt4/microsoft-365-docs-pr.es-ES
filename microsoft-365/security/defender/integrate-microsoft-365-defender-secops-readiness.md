---
title: Paso 2. Realizar una evaluación de preparación de integración SOC con el marco de confianza cero
description: Los conceptos básicos de realizar una evaluación de preparación de integración SOC con el marco de confianza cero al integrar Microsoft 365 Defender en las operaciones de seguridad.
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
localization_priority: Normal
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
ms.openlocfilehash: 27cbc0ec7286812cebc500952bc68adad3586eb8
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623874"
---
# <a name="step-2-perform-a-soc-integration-readiness-assessment-using-the-zero-trust-framework"></a>Paso 2. Realizar una evaluación de preparación de integración SOC con el marco de confianza cero

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Una vez definidas las funciones principales del equipo del Centro de operaciones de seguridad (SOC), el siguiente paso para su organización es prepararse para la adopción de Microsoft Defender a través de un enfoque de confianza [cero.](/security/zero-trust/) La adopción puede ayudarle a determinar los requisitos necesarios para implementar Microsoft 365 Defender con prácticas modernas líderes del sector, al tiempo que evalúa las capacidades de Defender en su entorno. 

Este enfoque se basa en una base sólida de protecciones e incluye áreas clave como identidad, puntos de conexión (dispositivos), datos, aplicaciones, infraestructura y redes. El equipo de evaluación de preparación determinará las áreas en las que aún no se ha cumplido un requisito fundamental para habilitar Microsoft 365 Defender y necesitará corrección. 

Estos son algunos de los elementos que tendrán que corregirse para que el SOC optimice completamente los procesos en el SOC:

- **Identidad:**     Dominios heredados de Servicios de dominio de Active Directory (AD DS), sin plan MFA, sin inventario de cuentas con privilegios y otros.
- **Extremos (dispositivos):**  Gran número de sistemas operativos heredados, inventario de dispositivos limitado y otros.
- **Datos y aplicaciones:**    Falta de estándares de gobierno de datos, ningún inventario de aplicaciones personalizadas que no se integrarán.
- **Infraestructura:**   Gran número de licencias SaaS sin licencia, sin seguridad de contenedor y otras.
- **Redes:**   Problemas de rendimiento debido a un ancho de banda bajo, red plana, problemas de seguridad inalámbrica y otros.

Las organizaciones también deben seguir el [artículo de Microsoft 365 Defender](m365d-enable.md) para capturar el conjunto de requisitos de configuración de línea base. Estos pasos determinarán a su vez las actividades de corrección que los equipos de SOC tendrán que llevar a cabo para desarrollar eficazmente casos de uso. 

Los procedimientos de adopción y la creación de casos de uso se describen en los pasos 3 y 4.

## <a name="next-step"></a>Paso siguiente

[Paso 3. Plan for Microsoft 365 Defender integration with your SOC catalog of services](integrate-microsoft-365-defender-secops-services.md)
