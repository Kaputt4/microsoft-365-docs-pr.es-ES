---
title: Bloqueo de bucles de distribución de comentarios
description: El bloqueo de bucles de comentarios, también denominado protección rápida, forma parte de las funcionalidades de bloqueo y contención del comportamiento en Microsoft Defender para punto de conexión
keywords: bloqueo del comportamiento, protección rápida, bloqueo de comentarios, Microsoft Defender para punto de conexión
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 42e3a8ac53d407e19457ab84cad85a1a3bcbcc92
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68194321"
---
# <a name="feedback-loop-blocking"></a>Bloqueo de bucles de distribución de comentarios

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

## <a name="overview"></a>Información general

El bloqueo de bucles de comentarios, también conocido como protección rápida, es un componente de [las funcionalidades de bloqueo y contención del comportamiento](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) en [Microsoft Defender para punto de conexión](/windows/security/threat-protection/). Con el bloqueo de bucles de comentarios, los dispositivos de toda la organización están mejor protegidos frente a ataques. 

## <a name="how-feedback-loop-blocking-works"></a>Funcionamiento del bloqueo de bucles de comentarios

Cuando se detecta un comportamiento o archivo sospechoso, como por [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), se envía información sobre ese artefacto a varios clasificadores. El motor de bucle de protección rápida inspecciona y correlaciona la información con otras señales para llegar a una decisión sobre si bloquear un archivo. La comprobación y clasificación de artefactos se produce rápidamente. Esto provoca un bloqueo rápido del malware confirmado y impulsa la protección en todo el ecosistema. 

Con una protección rápida, se puede detener un ataque en un dispositivo, otros dispositivos de la organización y dispositivos de otras organizaciones, a medida que un ataque intenta ampliar su posición.


## <a name="configuring-feedback-loop-blocking"></a>Configuración del bloqueo de bucle de comentarios

Si su organización usa Defender para punto de conexión, el bloqueo de bucles de comentarios está habilitado de forma predeterminada. Sin embargo, la protección rápida se produce a través de una combinación de funcionalidades de Defender para punto de conexión, características de protección de aprendizaje automático y uso compartido de señales entre los servicios de seguridad de Microsoft. Asegúrese de que las siguientes características y funcionalidades de Defender para punto de conexión están habilitadas y configuradas:

- [líneas base de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Dispositivos incorporados a Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR en modo bloqueo](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Reducción de la superficie expuesta a ataques](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Protección de próxima generación](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-articles"></a>Artículos relacionados

- [Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)

- [(Blog) Bloqueo y contención del comportamiento: Transformación de la óptica en protección](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Recursos de Microsoft Defender para punto de conexión útiles](/microsoft-365/security/defender-endpoint/helpful-resources)
