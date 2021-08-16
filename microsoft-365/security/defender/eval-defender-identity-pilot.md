---
title: Piloto de Microsoft Defender para identidad
description: Pilot Microsoft Defender for Identity, set benchmarks, take tutorials on reconnaissance, compromised credential, lateral movement, domain dominance, and exfiltration alerts, among others.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 70957d49f818424062002b8604854bf3bd5e60cb
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58252490"
---
# <a name="pilot-microsoft-defender-for-identity"></a>Piloto de Microsoft Defender para identidad


**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 3 de 3](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Identity. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-identity-overview.md).

Siga estos pasos para configurar y configurar el piloto de Microsoft Defender para la identidad. Tenga en cuenta que las recomendaciones no incluyen la configuración de un grupo piloto. El procedimiento recomendado es continuar e instalar el sensor en todos los servidores que ejecutan Servicios de dominio de Active Directory (AD DS) y Servicios federados de Active Directory (AD FS).

![Pasos para agregar Microsoft Defender for Identity al entorno de evaluación de Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

En la tabla siguiente se describen los pasos de la ilustración.

- [Paso 1: Configurar recomendaciones comparativas para su entorno de identidad](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [Paso 2: Probar capacidades: tutoriales para identificar y corregir diferentes tipos de ataques ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>Paso 1. Configurar recomendaciones de referencia para su entorno de identidad

Microsoft proporciona recomendaciones de referencia de seguridad para los clientes que usan los servicios de Microsoft Cloud. Azure [Security Benchmark](/security/benchmark/azure/overview) (ASB) proporciona recomendaciones y procedimientos recomendados prescriptivos para ayudar a mejorar la seguridad de las cargas de trabajo, los datos y los servicios en Azure.

Estas recomendaciones de referencia incluyen la línea [base de seguridad de Azure para Microsoft Defender para Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline). La implementación de estas recomendaciones puede tardar algún tiempo en planearse e implementarse. Aunque aumentarán considerablemente la seguridad del entorno de identidad, no deben impedir que continúes evaluando e implementando Microsoft Defender para Identity. Estos se proporcionan aquí para su conocimiento.

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>Paso 2. Capacidades de prueba: tutoriales para identificar y corregir diferentes tipos de ataques

La documentación de Microsoft Defender para identidades incluye una serie de tutoriales que le guían por el proceso de identificación y corrección de varios tipos de ataques.

Pruebe los tutoriales de Defender for Identity:
- [Alertas de reconocimiento](/defender-for-identity/reconnaissance-alerts)
- [Alertas de credenciales comprometidas](/defender-for-identity/compromised-credentials-alerts)
- [Alertas de movimiento lateral](/defender-for-identity/lateral-movement-alerts)
- [Alertas de dominio dominante](/defender-for-identity/domain-dominance-alerts)
- [Alertas de exfiltración](/defender-for-identity/exfiltration-alerts)
- [Investigar a un usuario](/defender-for-identity/investigate-a-user)
- [Investigar un equipo](/defender-for-identity/investigate-a-computer)
- [Investigar rutas de movimiento lateral](/defender-for-identity/investigate-lateral-movement-path)
- [Investigar entidades](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>Siguientes pasos

[Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la introducción a [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)