---
title: Habilitar el entorno de evaluación para Microsoft Cloud App Security
description: Obtenga información sobre la arquitectura de MCAS dentro de Microsoft Defender Office 365 y comprenda las interacciones entre los Microsoft 365 Defender productos.
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 761a8fcb3c6f7efe82c542001dac1f62eb365f1473268df0866bb5dfae0ed302
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863197"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>Habilitar el entorno de evaluación para Microsoft Cloud App Security


**Se aplica a:**

- Microsoft 365 Defender

Este artículo es [el paso 2 de 2](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Cloud App Security. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-mcas-overview.md).

En este artículo se explica el proceso de acceso al portal de Cloud App Security y la configuración de la integración necesaria para recopilar datos de tráfico de aplicaciones en la nube.

Para descubrir las aplicaciones en la nube que se usan en el entorno, puede realizar una o ambas de las siguientes acciones:

- Para empezar a trabajar rápidamente con Cloud Discovery, integre con Microsoft Defender para Endpoint. Esta integración nativa le permite empezar inmediatamente a recopilar datos sobre el tráfico en la nube en Windows 10 dispositivos, en y fuera de la red.
- Para descubrir todas las aplicaciones en la nube a las que acceden todos los dispositivos conectados a la red, implemente el recopilador de registros Cloud App Security en los firewalls y otros servidores proxy. Esto recopila datos de los puntos de conexión y los envía a Cloud App Security para su análisis. Cloud App Security se integra de forma nativa con algunos servidores proxy de terceros para obtener aún más funcionalidades.

En este artículo se incluyen instrucciones para ambos métodos.

Siga estos pasos para configurar Microsoft Cloud App Security.

![Pasos para habilitar Microsoft Microsoft Cloud App Security en el entorno de evaluación de Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [Paso 1. Conectar al portal de Cloud App Security web](#step-1-connect-to-the-cloud-app-security-portal)
- [Paso 2. Integrar con Microsoft Defender para endpoint](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [Paso 3. Implementar el Cloud App Security de registro en los firewalls y otros servidores proxy](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [Paso 4. Ver el panel de detección en la nube para ver qué aplicaciones se usan en su organización](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>Paso 1. Conectar al portal de Cloud App Security web

Para comprobar las licencias y conectarse al portal de Cloud App Security, vea [Inicio rápido: Introducción a Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security). 

Si no puede conectarse inmediatamente al portal, es posible que deba agregar la dirección IP a la lista de permitidos del firewall. Consulte [Configuración básica para Cloud App Security](/cloud-app-security/general-setup).

Si aún tiene problemas, revise [Requisitos de red](/cloud-app-security/network-requirements).

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Paso 2. Integrar con Microsoft Defender para endpoint

Microsoft Cloud App Security se integra con Microsoft Defender para Endpoint de forma nativa. La integración simplifica el lanzamiento de Cloud Discovery, amplía las capacidades de Cloud Discovery más allá de la red corporativa y habilita la investigación basada en dispositivos. Esta integración muestra los servicios y aplicaciones en la nube a los que se accede desde dispositivos Windows 10 administración de IT. 

Si ya has configurado Microsoft Defender para Endpoint, configurar la integración con Cloud App Security es un botón de alternancia en Microsoft 365 Defender. Una vez activada la integración, puede volver al portal de Cloud App Security y ver datos enriquecidos en el Panel de detección de nube.

Para realizar estas tareas, vea [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration). 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>Paso 3. Implementar el Cloud App Security de registro en los firewalls y otros servidores proxy

Para obtener cobertura en todos los dispositivos conectados a la red, implemente el recopilador de registros de Cloud App Security en los firewalls y otros servidores proxy para recopilar datos de los puntos de conexión y enviarlos a Cloud App Security para su análisis. 

Si usa una de las siguientes puertas de enlace web seguras (SWG), Cloud App Security una implementación e integración sin problemas:
- Zscaler
- iboss
- Corrata
- Menlo Security

Para obtener más información sobre la integración con estos dispositivos de red, consulte [Configurar la detección en la nube.](/cloud-app-security/set-up-cloud-discovery) 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Paso 4. Ver el panel de detección en la nube para ver qué aplicaciones se usan en su organización

El panel de detección de nube está diseñado para ofrecerte más información sobre cómo se usan las aplicaciones en la nube en tu organización. Proporciona una visión general general de los tipos de aplicaciones que se usan, las alertas abiertas y los niveles de riesgo de las aplicaciones de la organización. 

Para empezar a usar el panel de detección en la nube, consulta [Trabajar con aplicaciones detectadas.](/cloud-app-security/discovered-apps)

## <a name="next-steps"></a>Pasos siguientes

Paso 3 de 3: [Piloto Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

Vuelva a la introducción a [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)