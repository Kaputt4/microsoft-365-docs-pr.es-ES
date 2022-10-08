---
title: Paso 2. Realizar una evaluación de la preparación de integración de SOC mediante Confianza cero Framework
description: Los conceptos básicos de realizar una evaluación de la preparación de integración de SOC mediante Confianza cero Framework al integrar Microsoft 365 Defender en las operaciones de seguridad.
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
- m365-security
- m365solution-m365dsecops
- tier2
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c4c01f98f38097e45b53cec763419dbdd1209ec8
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68051594"
---
# <a name="step-2-perform-a-soc-integration-readiness-assessment-using-the-zero-trust-framework"></a>Paso 2. Realizar una evaluación de la preparación de integración de SOC mediante Confianza cero Framework

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Una vez definidas las funciones principales del equipo de Security Operations Center (SOC), el siguiente paso para su organización es prepararse para la adopción de Microsoft 365 Defender a través de un [enfoque de Confianza cero](/security/zero-trust/). La adopción puede ayudarle a determinar los requisitos necesarios para implementar Microsoft 365 Defender mediante prácticas modernas líderes del sector, al tiempo que evalúa las funcionalidades de Microsoft 365 Defender en su entorno.

Este enfoque se basa en una sólida base de protecciones e incluye áreas clave como la identidad, los puntos de conexión (dispositivos), los datos, las aplicaciones, la infraestructura y las redes. El equipo de evaluación de preparación determinará las áreas en las que aún no se ha cumplido un requisito fundamental para habilitar Microsoft 365 Defender y necesitará una corrección.

Los siguientes son algunos de los elementos que se deben corregir para que el SOC optimice completamente los procesos en el SOC:

- **Identidad:** Dominios heredados de Active Directory local Domain Services (AD DS), sin plan mfa, sin inventario de cuentas con privilegios y otros.
- **Puntos de conexión (dispositivos):** Gran número de sistemas operativos heredados, inventario limitado de dispositivos y otros.
- **Datos y aplicaciones:**  Falta de estándares de gobernanza de datos, no hay inventario de aplicaciones personalizadas que no se integrarán.
- **Infraestructura:** Gran número de licencias SaaS no autorizadas, sin seguridad de contenedor y otras.
- **Redes:** Problemas de rendimiento debidos a un ancho de banda bajo, una red plana, problemas de seguridad inalámbrica y otros.

Las organizaciones también deben seguir el artículo [activar Microsoft 365 Defender](m365d-enable.md) para capturar el conjunto de líneas base de los requisitos de configuración. A su vez, estos pasos determinarán las actividades de corrección que los equipos de SOC tendrán que llevar a cabo para desarrollar casos de uso de forma eficaz. 

Los procedimientos de adopción y la creación de casos de uso se describen en los pasos 3 y 4.

## <a name="next-step"></a>Paso siguiente

[Paso 3. Planeamiento de Microsoft 365 Defender integración con el catálogo de servicios de SOC](integrate-microsoft-365-defender-secops-services.md)
