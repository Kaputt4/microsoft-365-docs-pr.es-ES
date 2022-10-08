---
title: Contención y bloqueo de comportamiento del cliente
description: El bloqueo del comportamiento del cliente forma parte de las funcionalidades de bloqueo y contención del comportamiento en Microsoft Defender para punto de conexión
keywords: bloqueo del comportamiento, protección rápida, comportamiento del cliente, Microsoft Defender para punto de conexión
ms.pagetype: security
ms.subservice: mde
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
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 6a58cef549f8a3e9453d923f5db08503eb8e727d
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68151593"
---
# <a name="client-behavioral-blocking"></a>Contención y bloqueo de comportamiento del cliente

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataforma**
- Windows

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Información general

El bloqueo del comportamiento del cliente es un componente de [las funcionalidades de bloqueo y contención del comportamiento](behavioral-blocking-containment.md) en Defender para punto de conexión. A medida que se detectan comportamientos sospechosos en los dispositivos (también conocidos como clientes o puntos de conexión), los artefactos (como archivos o aplicaciones) se bloquean, comprueban y corrigen automáticamente.

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protección de la nube y el cliente" lightbox="images/pre-execution-and-post-execution-detection-engines.png":::

La protección antivirus funciona mejor cuando se empareja con la protección en la nube.

## <a name="how-client-behavioral-blocking-works"></a>Funcionamiento del bloqueo del comportamiento del cliente

[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) puede detectar comportamientos sospechosos, código malintencionado, ataques sin archivos y en memoria, etc. en un dispositivo. Cuando se detectan comportamientos sospechosos, Microsoft Defender Antivirus supervisa y envía esos comportamientos sospechosos y sus árboles de procesos al servicio de protección en la nube. El aprendizaje automático diferencia entre las aplicaciones malintencionadas y los buenos comportamientos en milisegundos y clasifica cada artefacto. En tiempo casi real, en cuanto se detecta que un artefacto es malintencionado, se bloquea en el dispositivo.

Cada vez que se detecta un comportamiento sospechoso, se genera una [alerta](alerts-queue.md) y es visible mientras se detectó y detuvo el ataque; las alertas, como una "alerta de acceso inicial", se desencadenan y aparecen en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) (anteriormente Microsoft 365 Defender).

El bloqueo del comportamiento del cliente es eficaz porque no solo ayuda a evitar que se inicie un ataque, sino que puede ayudar a detener un ataque que ha comenzado a ejecutarse. Además, con [el bloqueo de bucle de comentarios](feedback-loop-blocking.md) (otra funcionalidad de bloqueo y contención del comportamiento), los ataques se evitan en otros dispositivos de la organización.

## <a name="behavior-based-detections"></a>Detecciones basadas en comportamiento

Las detecciones basadas en comportamiento se denominan de acuerdo con la [matriz de ATT de MITRE&CK para empresas](https://attack.mitre.org/matrices/enterprise). La convención de nomenclatura ayuda a identificar la fase de ataque en la que se observó el comportamiento malintencionado:

|Táctica|Nombre de la amenaza de detección|
|---|---|
|Acceso inicial|`Behavior:Win32/InitialAccess.*!ml`|
|Ejecución|`Behavior:Win32/Execution.*!ml`|
|Persistencia|`Behavior:Win32/Persistence.*!ml`|
|Elevación de privilegios|`Behavior:Win32/PrivilegeEscalation.*!ml`|
|Evasión de defensa|`Behavior:Win32/DefenseEvasion.*!ml`|
|Acceso a credenciales|`Behavior:Win32/CredentialAccess.*!ml`|
|Descubrimiento|`Behavior:Win32/Discovery.*!ml`|
|Movimiento lateral|`Behavior:Win32/LateralMovement.*!ml`|
|Colección|`Behavior:Win32/Collection.*!ml`|
|Comando y control|`Behavior:Win32/CommandAndControl.*!ml`|
|Filtración|`Behavior:Win32/Exfiltration.*!ml`|
|Impacto|`Behavior:Win32/Impact.*!ml`|
|Uncategorized|`Behavior:Win32/Generic.*!ml`|

> [!TIP]
> Para obtener más información sobre amenazas específicas, consulte **[actividad de amenazas globales recientes](https://www.microsoft.com/wdsi/threats)**.

## <a name="configuring-client-behavioral-blocking"></a>Configuración del bloqueo del comportamiento del cliente

Si su organización usa Defender para punto de conexión, el bloqueo del comportamiento del cliente está habilitado de forma predeterminada. Sin embargo, para beneficiarse de todas las funcionalidades de Defender para punto de conexión, incluido el [bloqueo y la contención del comportamiento](behavioral-blocking-containment.md), asegúrese de que las siguientes características y funcionalidades de Defender para punto de conexión están habilitadas y configuradas:

- [Líneas base de Defender para punto de conexión](configure-machines-security-baseline.md)
- [Dispositivos incorporados a Defender para punto de conexión](onboard-configure.md)
- [EDR en modo bloqueo](edr-in-block-mode.md)
- [Reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
- [Protección de última generación](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware y otras funcionalidades de protección contra amenazas)

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
