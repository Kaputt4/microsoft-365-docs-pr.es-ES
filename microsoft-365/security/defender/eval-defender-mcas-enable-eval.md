---
title: Habilitación del entorno de evaluación para Microsoft Defender for Cloud Apps
description: Conozca la arquitectura de Defender for Cloud Apps en Microsoft Defender para Office 365 y comprenda las interacciones entre los productos de Microsoft 365 Defender.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: 695446ad061a2e727c347ac1bea15e59451b34d0
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072929"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-cloud-apps"></a>Habilitación del entorno de evaluación para Microsoft Defender for Cloud Apps

**Se aplica a:**

- Microsoft 365 Defender

Este artículo es el [paso 2 del 2](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Cloud Apps. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-mcas-overview.md).

Este artículo le guiará a través del proceso de acceso al portal de Defender for Cloud Apps y la configuración de la integración necesaria para recopilar datos de tráfico de aplicaciones en la nube.

Para detectar las aplicaciones en la nube que se usan en su entorno, puede implementar uno o ambos de los métodos siguientes:

- Empiece a trabajar rápidamente con Cloud Discovery mediante la integración con Microsoft Defender para punto de conexión. Esta integración nativa le permite empezar inmediatamente a recopilar datos sobre el tráfico en la nube en los dispositivos Windows 10 y Windows 11, dentro y fuera de la red.
- Para detectar todas las aplicaciones en la nube a las que acceden todos los dispositivos conectados a la red, implemente el recopilador de registros de Defender for Cloud Apps en los firewalls y otros servidores proxy. Esta implementación ayuda a recopilar datos de los puntos de conexión y los envía a Defender for Cloud Apps para su análisis. Defender for Cloud Apps se integra de forma nativa con algunos servidores proxy de terceros para obtener aún más funcionalidades.

En este artículo se incluyen instrucciones para ambos métodos.

Siga estos pasos para configurar Microsoft Defender for Cloud Apps.

:::image type="content" source="../../media/defender/m365-defender-mcas-eval-enable-steps.png" alt-text="Los pasos para habilitar Microsoft Microsoft Defender for Cloud Apps en el entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-mcas-eval-enable-steps.png":::

- [Paso 1. Conexión al portal de Defender for Cloud Apps](#step-1)
- [Paso 2. Integración con Microsoft Defender para punto de conexión](#step-2)
- [Paso 3. Implementación del recopilador de registros de Defender for Cloud Apps en los firewalls y otros servidores proxy](#step-3)
- [Paso 4. Vea el panel de Cloud Discovery para ver qué aplicaciones se usan en su organización.](#step-4)

<a name="step-1"></a>

## <a name="step-1-connect-to-the-defender-for-cloud-apps-portal"></a>Paso 1. Conexión al portal de Defender for Cloud Apps

Para comprobar las licencias y conectarse al portal de Defender for Cloud Apps, consulte [Inicio rápido: Introducción a Microsoft Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security).

Si no puede conectarse inmediatamente al portal, es posible que tenga que agregar la dirección IP a la lista de permitidos del firewall. Consulte [Configuración básica para Defender for Cloud Apps](/cloud-app-security/general-setup).

Si sigue teniendo problemas, revise [Requisitos de red](/cloud-app-security/network-requirements).

<a name="step-2"></a>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Paso 2. Integración con Microsoft Defender para punto de conexión

Microsoft Defender for Cloud Apps se integra con Microsoft Defender para punto de conexión de forma nativa. La integración simplifica la implementación de Cloud Discovery, amplía las funcionalidades de Cloud Discovery más allá de la red corporativa y permite la investigación basada en dispositivos. Esta integración revela las aplicaciones en la nube y los servicios a los que se accede desde dispositivos de Windows 10 y Windows 11 administrados por TI.

Si ya ha configurado Microsoft Defender para punto de conexión, la configuración de la integración con Defender for Cloud Apps es un botón de alternancia en Microsoft 365 Defender. Una vez activada la integración, puede volver al portal de Defender for Cloud Apps y ver datos enriquecidos en el panel de Cloud Discovery.

Para realizar estas tareas, consulte [Microsoft Defender para punto de conexión integración con Microsoft Defender for Cloud Apps](/cloud-app-security/mde-integration).

<a name="step-3"></a>

## <a name="step-3-deploy-the-defender-for-cloud-apps-log-collector-on-your-firewalls-and-other-proxies"></a>Paso 3. Implementación del recopilador de registros de Defender for Cloud Apps en los firewalls y otros servidores proxy

Para obtener cobertura en todos los dispositivos conectados a la red, implemente el recopilador de registros de Defender for Cloud Apps en los firewalls y otros servidores proxy para recopilar datos de los puntos de conexión y enviarlos a Defender for Cloud Apps para su análisis.

Si usa una de las siguientes puertas de enlace web seguras (SWG), Defender for Cloud Apps proporciona una implementación e integración sin problemas:

- Zscaler
- iboss
- Corrata
- Menlo Security

Para obtener más información sobre la integración con estos dispositivos de red, consulte [Configuración de Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).

<a name="step-4"></a>

## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Paso 4. Vea el panel de Cloud Discovery para ver qué aplicaciones se usan en su organización.

El panel de Cloud Discovery está diseñado para proporcionarle más información sobre cómo se usan las aplicaciones en la nube en su organización. Proporciona una visión general de los tipos de aplicaciones que se usan, las alertas abiertas y los niveles de riesgo de las aplicaciones de su organización.

Para empezar a usar el panel de Cloud Discovery, consulte [Trabajar con aplicaciones detectadas](/cloud-app-security/discovered-apps).

## <a name="next-steps"></a>Pasos siguientes

Paso 3 de 3: [Microsoft Defender for Cloud Apps piloto](eval-defender-mcas-pilot.md)

Vuelva a la introducción para [Evaluar Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
