---
title: Restaurar archivos en cuarentena en el Antivirus de Windows Defender
description: Puede restaurar archivos y carpetas que Microsoft Defender Antivirus pusieron en cuarentena.
keywords: ''
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/19/2021
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: conceptual
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: b6beeb4039891403ac8645117d4c55f0c2be9b51
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68626037"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>Restaurar archivos en cuarentena en el Antivirus de Windows Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Si Microsoft Defender Antivirus está configurado para detectar y corregir amenazas en el dispositivo, Microsoft Defender Antivirus pone en cuarentena los archivos sospechosos. Si está seguro de que un archivo en cuarentena no es una amenaza, puede restaurarlo.

1. Abra **Seguridad de Windows**.
2. Seleccione **Virus & protección contra amenazas** y, a continuación, haga clic en **Historial de protección**.
3. En la lista de todos los elementos recientes, filtre por **Elementos en cuarentena**.
4. Seleccione un elemento que quiera conservar y realice una acción, como restaurar.

> [!TIP]
> La restauración de un archivo desde la cuarentena también se puede realizar mediante el símbolo del sistema. Consulte [Restauración de un archivo desde la cuarentena](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine). 

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

- [Configuración de la corrección de exámenes](configure-remediation-microsoft-defender-antivirus.md)
- [Revisión de los resultados del examen](review-scan-results-microsoft-defender-antivirus.md)
- [Configuración y validación de exclusiones basadas en el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configuración y validación de exclusiones para archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configuración de exclusiones de antivirus de Microsoft Defender en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)