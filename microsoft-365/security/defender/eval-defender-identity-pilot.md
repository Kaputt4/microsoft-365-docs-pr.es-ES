---
title: Microsoft Defender for Identity piloto
description: Microsoft Defender for Identity piloto, establecer pruebas comparativas, realizar tutoriales sobre reconocimiento, credenciales comprometidas, movimiento lateral, dominación de dominio y alertas de filtración, entre otros.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: c5ca701732bd76eff22eeeadf64502f11e2ca5cc
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68086099"
---
# <a name="pilot-microsoft-defender-for-identity"></a>Microsoft Defender for Identity piloto


**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 3 del 3](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Identity. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-identity-overview.md).

Siga estos pasos para configurar y configurar el piloto de Microsoft Defender para la identidad. Tenga en cuenta que las recomendaciones no incluyen la configuración de un grupo piloto. El procedimiento recomendado es continuar e instalar el sensor en todos los servidores que ejecutan Servicios de dominio de Active Directory (AD DS) y Servicios federados de Active Directory (AD FS).

:::image type="content" source="../../media/defender/m365-defender-identity-pilot-steps.png" alt-text="Los pasos para la Microsoft Defender for Identity piloto en el entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-identity-pilot-steps.png":::

En la tabla siguiente se describen los pasos de la ilustración.

- [Paso 1: Configuración de recomendaciones de pruebas comparativas para el entorno de identidad](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [Paso 2: Probar funcionalidades: tutoriales para identificar y corregir diferentes tipos de ataques ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>Paso 1. Configuración de recomendaciones de pruebas comparativas para el entorno de identidad

Microsoft proporciona recomendaciones de pruebas comparativas de seguridad para los clientes que usan servicios de Microsoft Cloud. [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) proporciona procedimientos recomendados y recomendaciones prescriptivas para ayudar a mejorar la seguridad de las cargas de trabajo, los datos y los servicios en Azure.

Estas recomendaciones de pruebas comparativas incluyen [la línea base de seguridad de Azure para Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline). La implementación de estas recomendaciones puede tardar algún tiempo en planearse e implementarse. Aunque aumentarán considerablemente la seguridad del entorno de identidad, no deben impedir que continúe e implemente Microsoft Defender for Identity. Estos se proporcionan aquí para su conciencia.

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>Paso 2. Probar funcionalidades: tutoriales para identificar y corregir diferentes tipos de ataque

La documentación Microsoft Defender for Identity incluye una serie de tutoriales que le guiarán por el proceso de identificación y corrección de varios tipos de ataque.

Pruebe los tutoriales de Defender for Identity:
- [Alertas de reconocimiento](/defender-for-identity/reconnaissance-alerts)
- [Alertas de credenciales en peligro](/defender-for-identity/compromised-credentials-alerts)
- [Alertas de movimiento lateral](/defender-for-identity/lateral-movement-alerts)
- [Alertas de dominación de dominio](/defender-for-identity/domain-dominance-alerts)
- [Alertas de filtración](/defender-for-identity/exfiltration-alerts)
- [Investigación de un usuario](/defender-for-identity/investigate-a-user)
- [Investigación de un equipo](/defender-for-identity/investigate-a-computer)
- [Investigar rutas de movimiento lateral](/defender-for-identity/investigate-lateral-movement-path)
- [Investigar entidades](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>Pasos siguientes

[Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la introducción para [Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)