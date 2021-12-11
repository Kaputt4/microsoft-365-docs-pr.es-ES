---
title: Configurar Antivirus de Microsoft Defender con WMI
description: Obtenga información sobre cómo configurar y administrar Antivirus de Microsoft Defender mediante scripts WMI para recuperar, modificar y actualizar la configuración en Microsoft Defender para endpoint.
keywords: wmi, scripts, instrumental de administración de windows, configuración
ms.prod: m365-security
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
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: c8057a971576d5511440ac009acd6eab55b302e9
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168371"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Use Windows Instrumental de administración de administración (WMI) para configurar y administrar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

Windows Instrumental de administración (WMI) es una interfaz de scripting que permite recuperar, modificar y actualizar la configuración.

Obtenga más información sobre WMI en la biblioteca de administración del sistema de [Microsoft Developer Network.](/windows/win32/wmisdk/wmi-start-page)

Antivirus de Microsoft Defender tiene varias clases WMI específicas que se pueden usar para realizar la mayoría de las mismas funciones que la directiva de grupo y otras herramientas de administración. Muchas de las clases son análogas a [los cmdlets de PowerShell de Defender para la nube.](use-powershell-cmdlets-microsoft-defender-antivirus.md)

La biblioteca de Windows Defender referencia del proveedor [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) de MSDN enumera las clases WMI disponibles para Antivirus de Microsoft Defender e incluye scripts de ejemplo.

Los cambios realizados con WMI afectarán a la configuración local en el punto de conexión donde se implementan o realizan los cambios. Esto significa que las implementaciones de directivas con directiva de grupo, Microsoft Endpoint Configuration Manager o Microsoft Intune pueden sobrescribir los cambios realizados con WMI. 

Puede configurar [qué opciones se pueden invalidar localmente con invalidaciones de directiva local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Temas relacionados

- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
