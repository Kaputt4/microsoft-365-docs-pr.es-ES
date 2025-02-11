---
title: Configuración de Microsoft Defender Antivirus con WMI
description: Obtenga información sobre cómo configurar y administrar Microsoft Defender Antivirus mediante scripts WMI para recuperar, modificar y actualizar la configuración en Microsoft Defender para punto de conexión.
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
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: b12c7fa681d62b531aad4655a3daa7cd652696d3
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68228764"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Uso de Instrumental de administración de Windows (WMI) para configurar y administrar Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Instrumental de administración de Windows (WMI) es una interfaz de scripting que permite recuperar, modificar y actualizar la configuración.

Obtenga más información sobre WMI en la [biblioteca administración del sistema de red para desarrolladores de Microsoft](/windows/win32/wmisdk/wmi-start-page).

Microsoft Defender Antivirus tiene varias clases WMI específicas que se pueden usar para realizar la mayoría de las mismas funciones que directiva de grupo y otras herramientas de administración. Muchas de las clases son análogas a los [cmdlets de PowerShell de Defender for Cloud](use-powershell-cmdlets-microsoft-defender-antivirus.md).

La [biblioteca de referencia del proveedor WMIv2 de MSDN Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) enumera las clases WMI disponibles para Microsoft Defender Antivirus e incluye scripts de ejemplo.

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
