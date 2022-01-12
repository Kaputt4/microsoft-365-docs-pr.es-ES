---
title: Habilitar el entorno de evaluación para Microsoft Defender para aplicaciones en la nube
description: Obtenga información sobre la arquitectura de Defender para aplicaciones en la nube en Microsoft Defender para Office 365 y comprenda las interacciones entre los Microsoft 365 Defender productos.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9d0418b2f183884793be3c2d8a72f571d0072a61
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61933149"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-cloud-apps"></a>Habilitar el entorno de evaluación para Microsoft Defender para aplicaciones en la nube

**Se aplica a:**

- Microsoft 365 Defender

Este artículo es [el paso 2 de 2](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para aplicaciones en la nube. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-mcas-overview.md).

En este artículo se explica el proceso de acceso al portal de Defender for Cloud Apps y la configuración de la integración necesaria para recopilar datos de tráfico de aplicaciones en la nube.

Para descubrir las aplicaciones en la nube que se usan en el entorno, puede realizar una o ambas de las siguientes acciones:

- Para empezar a trabajar rápidamente con Cloud Discovery, integre con Microsoft Defender para Endpoint. Esta integración nativa le permite empezar inmediatamente a recopilar datos sobre el tráfico en la nube en Windows 10 y Windows 11 dispositivos, tanto en la red como fuera de la red.
- Para descubrir todas las aplicaciones en la nube a las que acceden todos los dispositivos conectados a la red, implemente el recopilador de registros defender para aplicaciones en la nube en los firewalls y otros servidores proxy. Esto recopila datos de los puntos de conexión y los envía a Defender para aplicaciones en la nube para su análisis. Defender for Cloud Apps se integra de forma nativa con algunos servidores proxy de terceros para obtener aún más funcionalidades.

En este artículo se incluyen instrucciones para ambos métodos.

Siga estos pasos para configurar Microsoft Defender para aplicaciones en la nube.

![Pasos para habilitar Microsoft Microsoft Defender para aplicaciones en la nube en el entorno de evaluación de Microsoft Defender.](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [Paso 1. Conectar al portal de Defender for Cloud Apps](#step-1)
- [Paso 2. Integrar con Microsoft Defender para endpoint](#step-2)
- [Paso 3. Implementar el recopilador de registros de Defender for Cloud Apps en los firewalls y otros servidores proxy](#step-3)
- [Paso 4. Ver el panel de detección en la nube para ver qué aplicaciones se usan en su organización](#step-4)

<a name="step-1"></a>

## <a name="step-1-connect-to-the-defender-for-cloud-apps-portal"></a>Paso 1. Conectar al portal de Defender for Cloud Apps

Para comprobar las licencias y conectarse al portal de Defender para Aplicaciones en la nube, consulte Inicio rápido: Introducción a [Microsoft Defender para aplicaciones en la nube.](/cloud-app-security/getting-started-with-cloud-app-security)

Si no puede conectarse inmediatamente al portal, es posible que deba agregar la dirección IP a la lista de permitidos del firewall. Consulta [Configuración básica de Defender para aplicaciones en la nube.](/cloud-app-security/general-setup)

Si aún tiene problemas, revise [Requisitos de red](/cloud-app-security/network-requirements).

<a name="step-2"></a>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Paso 2. Integrar con Microsoft Defender para endpoint

Microsoft Defender para Aplicaciones en la nube se integra con Microsoft Defender para Endpoint de forma nativa. La integración simplifica el lanzamiento de Cloud Discovery, amplía las capacidades de Cloud Discovery más allá de la red corporativa y habilita la investigación basada en dispositivos. Esta integración muestra los servicios y aplicaciones en la nube a los que se accede desde dispositivos administrados por WINDOWS 10 y Windows 11 dispositivos.

Si ya has configurado Microsoft Defender para Endpoint, configurar la integración con Defender para Aplicaciones en la nube es una alternancia en Microsoft 365 Defender. Una vez activada la integración, puedes volver al portal de Defender for Cloud Apps y ver datos enriquecidos en el Panel de detección de nube.

Para realizar estas tareas, consulte [Microsoft Defender for Endpoint integration with Microsoft Defender for Cloud Apps](/cloud-app-security/mde-integration).

<a name="step-3"></a>

## <a name="step-3-deploy-the-defender-for-cloud-apps-log-collector-on-your-firewalls-and-other-proxies"></a>Paso 3. Implementar el recopilador de registros de Defender for Cloud Apps en los firewalls y otros servidores proxy

Para obtener cobertura en todos los dispositivos conectados a la red, implemente el recopilador de registros defender para aplicaciones en la nube en los firewalls y otros servidores proxy para recopilar datos de los puntos de conexión y enviarlos a Defender para aplicaciones en la nube para su análisis.

Si usa una de las siguientes puertas de enlace web seguras (SWG), Defender for Cloud Apps proporciona una implementación e integración perfectas:

- Zscaler
- iboss
- Corrata
- Menlo Security

Para obtener más información sobre la integración con estos dispositivos de red, consulte [Configurar la detección en la nube.](/cloud-app-security/set-up-cloud-discovery)

<a name="step-4"></a>

## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Paso 4. Ver el panel de detección en la nube para ver qué aplicaciones se usan en su organización

El panel de detección de nube está diseñado para ofrecerte más información sobre cómo se usan las aplicaciones en la nube en tu organización. Proporciona una visión general general de los tipos de aplicaciones que se usan, las alertas abiertas y los niveles de riesgo de las aplicaciones de la organización.

Para empezar a usar el panel de detección en la nube, consulta [Trabajar con aplicaciones detectadas.](/cloud-app-security/discovered-apps)

## <a name="next-steps"></a>Siguientes pasos

Paso 3 de 3: [Piloto de Microsoft Defender para aplicaciones en la nube](eval-defender-mcas-pilot.md)

Vuelva a la introducción a [Evaluar Microsoft Defender para aplicaciones en la nube](eval-defender-mcas-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)
