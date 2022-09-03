---
title: Configuración del Antivirus de Microsoft Defender con WMI
description: Obtenga información sobre cómo configurar y administrar el Antivirus de Microsoft Defender mediante scripts WMI para recuperar, modificar y actualizar la configuración en Microsoft Defender para punto de conexión.
keywords: wmi, scripts, instrumentación de administración de Windows, configuración
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 9d18838f64d693caba643c0939a21abb66b2a284
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67577505"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Uso de Instrumental de administración de Windows (WMI) para configurar y administrar el Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Instrumental de administración de Windows (WMI) es una interfaz de scripting que permite recuperar, modificar y actualizar la configuración.

Obtenga más información sobre WMI en la [biblioteca administración del sistema de red para desarrolladores de Microsoft](/windows/win32/wmisdk/wmi-start-page).

Antivirus de Microsoft Defender tiene una serie de clases WMI específicas que se pueden usar para realizar la mayoría de las mismas funciones que directiva de grupo y otras herramientas de administración. Muchas de las clases son análogas a los [cmdlets de PowerShell de Defender for Cloud](use-powershell-cmdlets-microsoft-defender-antivirus.md).

La [biblioteca de referencia del proveedor WMIv2 de MSDN Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) enumera las clases WMI disponibles para el Antivirus de Microsoft Defender e incluye scripts de ejemplo.

Los cambios realizados con WMI afectarán a la configuración local en el punto de conexión donde se implementan o realizan los cambios. Esto significa que las implementaciones de directiva con directiva de grupo, Configuration Manager de punto de conexión de Microsoft o Microsoft Intune pueden sobrescribir los cambios realizados con WMI. 

Puede [configurar qué opciones se pueden invalidar localmente con invalidaciones de directiva local](configure-local-policy-overrides-microsoft-defender-antivirus.md).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-topics"></a>Temas relacionados

- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
