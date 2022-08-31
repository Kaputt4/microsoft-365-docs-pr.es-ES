---
title: Habilitación del entorno de evaluación para Microsoft Defender for Identity
description: Configure Microsoft Defender for Identity en Microsoft 365 Defender laboratorio de prueba o entorno piloto mediante la instalación de & configuración del sensor y la detección de administradores locales en otros equipos.
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
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 800410fe4faecde9a104242d5d4a1821ad8de86a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482260"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Habilitación del entorno de evaluación para Microsoft Defender for Identity

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 2 del 2](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Identity. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-identity-overview.md).

Siga estos pasos para configurar el entorno de Microsoft Defender for Identity. 

:::image type="content" source="../../media/defender/m365-defender-identity-eval-enable-steps.png" alt-text="Los pasos para habilitar Microsoft Defender for Identity en el entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-identity-eval-enable-steps.png":::

- [Paso 1. Configuración de la instancia de Defender for Identity](#step-1-set-up-the-defender-for-identity-instance)
- [Paso 2. Instalación y configuración del sensor](#step-2-install-and-configure-the-sensor)
- [Paso 3. Configuración del registro de eventos y del proxy en las máquinas con el sensor](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [Paso 4. Permitir que Defender for Identity identifique administradores locales en otros equipos](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>Paso 1. Configuración de la instancia de Defender for Identity

Inicie sesión en el portal de Defender for Identity para crear la instancia y, a continuación, conecte esta instancia al entorno de Active Directory. 

|  Paso | Descripción     |Más información  |
|---------|---------|---------|
|1     | Creación de la instancia de Defender for Identity        | [Inicio rápido: crear la instancia de Microsoft Defender for Identity](/defender-for-identity/install-step1)        |
|2     | Conexión de la instancia de Defender for Identity al bosque de Active Directory   | [Inicio rápido: Conexión al bosque de Active Directory](/defender-for-identity/install-step2)  |

## <a name="step-2-install-and-configure-the-sensor"></a>Paso 2. Instalación y configuración del sensor

A continuación, descargue, instale y configure el sensor de Defender for Identity en los controladores de dominio y los servidores de AD FS en el entorno local.

|  Paso | Descripción     |Más información  |
|---------|---------|---------|
|1     | Determine cuántos sensores de Microsoft Defender for Identity necesita.        | [Capacidad del plan para Microsoft Defender for Identity](/defender-for-identity/capacity-planning)   |
|2     | Descarga del paquete de configuración del sensor  |  [Inicio rápido: Descarga del paquete de configuración del sensor de Microsoft Defender for Identity](/defender-for-identity/install-step3)   |
|3     | Instalación del sensor de Defender for Identity    |  [Inicio rápido: Instalación del sensor de Microsoft Defender for Identity](/defender-for-identity/install-step4)       |
|4     | Configuración del sensor       |  [Configuración de Microsoft Defender for Identity sensor](/defender-for-identity/install-step5)   |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>Paso 3. Configuración del registro de eventos y del proxy en las máquinas con el sensor

En las máquinas en las que instaló el sensor, configure la recopilación de registros de eventos de Windows y la configuración del proxy de Internet para habilitar y mejorar las funcionalidades de detección.

|  Paso | Descripción     |Más información  |
|---------|---------|---------|
|1     | Configuración de la recopilación de registros de eventos de Windows         | [Configuración de la colección de eventos de Windows](/defender-for-identity/configure-windows-event-collection)        |
|2     | Configuración del proxy de Internet        | [Configurar el proxy de punto de conexión y las opciones de conectividad a Internet para el Sensor de Microsoft Defender for Identity](/defender-for-identity/configure-proxy)        |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>Paso 4. Permitir que Defender for Identity identifique administradores locales en otros equipos

La detección de rutas de movimiento lateral de Microsoft Defender for Identity se basa en consultas que identifican a los administradores locales en máquinas específicas. Estas consultas se realizan con el protocolo SAM-R mediante la cuenta de Defender for Identity Service. 

Para asegurarse de que los clientes y servidores de Windows permiten que su cuenta de Defender for Identity realice SAM-R, se debe realizar una modificación en directiva de grupo para agregar la cuenta de servicio de Defender for Identity además de las cuentas configuradas enumeradas en la directiva de acceso de red. Asegúrese de aplicar directivas de grupo a todos los equipos **excepto a los controladores de dominio**.

Para obtener instrucciones sobre cómo hacerlo, consulte [Configuración de Microsoft Defender for Identity para realizar llamadas remotas a SAM](/defender-for-identity/install-step8-samr). 

## <a name="next-steps"></a>Pasos siguientes

Paso 3 de 3: [Microsoft Defender for Identity piloto](eval-defender-identity-pilot.md)

Vuelva a la introducción para [Evaluar Microsoft Defender for Identity](eval-defender-identity-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
