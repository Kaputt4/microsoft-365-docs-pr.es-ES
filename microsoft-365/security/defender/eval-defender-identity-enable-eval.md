---
title: Habilitar el entorno de evaluación de Microsoft Defender para Identity, configurar la instancia MDI, instalar y configurar el sensor MDI, permitir que el sensor MDI detecte administradores locales
description: Configure Microsoft Defender for Identity en un entorno piloto Microsoft 365 Defender de prueba mediante la instalación de & la configuración del sensor y la descubriendo administradores locales en otros equipos.
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458564"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Habilitar el entorno de evaluación para Microsoft Defender for Identity

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 2 de 2](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Identity. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-identity-overview.md).

Siga estos pasos para configurar el entorno de Microsoft Defender para Identity. 

![Pasos para habilitar Microsoft Defender for Identity en el entorno de evaluación de Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [Paso 1. Configurar la instancia de Defender for Identity](#step-1-set-up-the-defender-for-identity-instance)
- [Paso 2. Instalar y configurar el sensor](#step-2-install-and-configure-the-sensor)
- [Paso 3. Configurar la configuración de proxy y registro de eventos en máquinas con el sensor](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [Paso 4. Permitir que Defender for Identity identifique administradores locales en otros equipos](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>Paso 1. Configurar la instancia de Defender for Identity

Inicie sesión en el portal de Defender for Identity para crear la instancia y, a continuación, conecte esta instancia al entorno de Active Directory. 

|  |Paso     |Más información  |
|---------|---------|---------|
|1     | Crear la instancia de Defender for Identity        | [Inicio rápido: crear la instancia de Microsoft Defender for Identity](/defender-for-identity/install-step1)        |
|2     | Conectar la instancia de Defender for Identity al bosque de Active Directory   | [Inicio rápido: Conectar al bosque de Active Directory](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>Paso 2. Instalar y configurar el sensor

A continuación, descargue, instale y configure el sensor Defender for Identity en los controladores de dominio y los servidores de AD FS en el entorno local.

|  |Paso     |Más información  |
|---------|---------|---------|
|1     | Determine cuántos sensores de Microsoft Defender para Identidad necesita.        | [Planear la capacidad de Microsoft Defender para Identity](/defender-for-identity/capacity-planning)   |
|2     | Descargar el paquete de instalación del sensor  |  [Inicio rápido: descargar el paquete de instalación del sensor de Microsoft Defender para identidad](/defender-for-identity/install-step3)   |
|3     | Instalar el sensor Defender for Identity    |  [Inicio rápido: instalar el sensor de Microsoft Defender para identidad](/defender-for-identity/install-step4)       |
|4      | Configurar el sensor       |  [Configuración de Microsoft Defender para la configuración del sensor de identidad ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>Paso 3. Configurar la configuración de proxy y registro de eventos en máquinas con el sensor

En las máquinas en las que instaló el sensor, configure la colección Windows de registros de eventos y la configuración de proxy de Internet para habilitar y mejorar las capacidades de detección.

|  |Paso     |Más información  |
|---------|---------|---------|
|1     | Configurar Windows de registro de eventos         | [Configurar Windows event (colección)](/defender-for-identity/configure-windows-event-collection)        |
|2     | Configurar la configuración de proxy de Internet        | [Configurar el proxy de extremo y la configuración de conectividad a Internet para el Sensor de identidad de Microsoft Defender para](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>Paso 4. Permitir que Defender for Identity identifique administradores locales en otros equipos

La detección de rutas de movimiento lateral de Microsoft Defender para identidad se basa en consultas que identifican a los administradores locales en máquinas específicas. Estas consultas se realizan con el protocolo SAM-R, mediante la cuenta defender para el servicio de identidad. 

Para asegurarse de que Windows clientes y servidores permiten que la cuenta de Defender for Identity realice SAM-R, se debe realizar una modificación en la directiva de grupo para agregar la cuenta de servicio Defender for Identity además de las cuentas configuradas que aparecen en la directiva de acceso a la red. Asegúrese de aplicar directivas de grupo a todos los equipos **excepto a los controladores de dominio**.

Para obtener instrucciones sobre cómo hacerlo, consulte [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr). 

## <a name="next-steps"></a>Pasos siguientes

Paso 3 de 3: [Piloto de Microsoft Defender para identidad](eval-defender-identity-pilot.md)

Vuelva a la introducción a [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)