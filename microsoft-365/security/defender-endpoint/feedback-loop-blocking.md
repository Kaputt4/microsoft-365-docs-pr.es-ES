---
title: Bloqueo de bucles de distribución de comentarios
description: El bloqueo de bucle de comentarios, también denominado protección rápida, forma parte de las capacidades de contención y bloqueo de comportamiento en Microsoft Defender para endpoint
keywords: bloqueo de comportamiento, protección rápida, bloqueo de comentarios, Microsoft Defender para endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842463"
---
# <a name="feedback-loop-blocking"></a>Bloqueo de bucles de distribución de comentarios

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Información general

El bloqueo de bucle de comentarios, también conocido como protección rápida, es un componente de las capacidades de bloqueo y [contención](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) del comportamiento en [Microsoft Defender para endpoint](/windows/security/threat-protection/). Con el bloqueo de bucle de comentarios, los dispositivos de toda la organización están mejor protegidos contra ataques. 

## <a name="how-feedback-loop-blocking-works"></a>Cómo funciona el bloqueo de bucle de comentarios

Cuando se detecta un comportamiento o archivo sospechoso, como por ejemplo [Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), la información sobre ese artefacto se envía a varios clasificadores. El motor de bucle de protección rápida inspecciona y correlaciona la información con otras señales para tomar una decisión sobre si se va a bloquear un archivo. La comprobación y clasificación de artefactos se produce rápidamente. Esto da como resultado un bloqueo rápido del malware confirmado e impulsa la protección en todo el ecosistema. 

Con la protección rápida en su lugar, se puede detener un ataque en un dispositivo, otros dispositivos de la organización y dispositivos de otras organizaciones, mientras un ataque intenta ampliar su posición.


## <a name="configuring-feedback-loop-blocking"></a>Configuración del bloqueo de bucle de comentarios

Si su organización usa Defender para endpoint, el bloqueo de bucle de comentarios está habilitado de forma predeterminada. Sin embargo, la protección rápida se produce a través de una combinación de funcionalidades de Defender para endpoints, características de protección de aprendizaje automático y uso compartido de señales en los servicios de seguridad de Microsoft. Asegúrese de que las siguientes características y funcionalidades de Defender for Endpoint están habilitadas y configuradas:

- [Líneas base de Microsoft Defender para puntos de conexión](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Dispositivos incorporados a Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR en modo bloqueo](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Reducción de la superficie expuesta a ataques](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Protección de última generación](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Artículos relacionados

- [Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)

- [(Blog) Bloqueo y contención de comportamiento: transformar la óptica en protección](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [ÚtilEs recursos de Microsoft Defender para puntos de conexión](/microsoft-365/security/defender-endpoint/helpful-resources)
