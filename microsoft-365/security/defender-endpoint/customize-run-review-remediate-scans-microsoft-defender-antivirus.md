---
title: Ejecución y personalización de exámenes programados y a petición
description: Personalización e inicio de exámenes Microsoft Defender Antivirus en puntos de conexión a través de la red
keywords: scan, schedule, customize, exclusions, exclude files, remediation, scan results, quarantine, remove threat, quick scan, full scan, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: conceptual
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 82cdf185f36bc337aa0c783d6d37a2fbb6e4036c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68635716"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Personalización, inicio y revisión de los resultados de los exámenes y correcciones de Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Puede usar समूह नीति, PowerShell e Instrumental de administración de Windows (WMI) para configurar exámenes de antivirus de Microsoft Defender. 

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
---|---
[Configuración y validación de exclusiones de archivos, carpetas y archivos abiertos por procesos en Microsoft Defender exámenes del Antivirus](configure-exclusions-microsoft-defender-antivirus.md) | Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas de los exámenes a petición, los exámenes programados y la supervisión y el examen de protección en tiempo real siempre activados.
[Configurar opciones de análisis del Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Puede configurar Microsoft Defender Antivirus para incluir determinados tipos de archivos de almacenamiento de correo electrónico, puntos de copia de seguridad o reanálisis, y archivos archivados (por ejemplo, archivos .zip) en los exámenes. También puede habilitar el examen de archivos de red
[Configuración de la corrección de exámenes](configure-remediation-microsoft-defender-antivirus.md) | Configure lo que Microsoft Defender Antivirus debe hacer cuando detecte una amenaza y cuánto tiempo deben conservarse los archivos en cuarentena en la carpeta de cuarentena.
[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Configurar exámenes periódicos (programados), incluidos cuándo se deben ejecutar y si se ejecutan como exámenes completos o rápidos
[Configuración y ejecución de exámenes](run-scan-microsoft-defender-antivirus.md) | Ejecución y configuración de exámenes a petición mediante PowerShell, Instrumental de administración de Windows o individualmente en puntos de conexión con la aplicación Seguridad de Windows
[Revisión de los resultados del examen](review-scan-results-microsoft-defender-antivirus.md) | Revise los resultados de los exámenes mediante Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows