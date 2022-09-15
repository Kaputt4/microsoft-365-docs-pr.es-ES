---
title: Ejecute y personalice los exámenes programados y a petición.
description: Personalización e inicio de exámenes del Antivirus de Microsoft Defender en puntos de conexión a través de la red
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
ms.topic: article
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 8b0e34ece48091b3abfd6cedb6dba12b791e3625
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694885"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Personalización, inicio y revisión de los resultados de los exámenes y correcciones del Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Puede usar directiva de grupo, PowerShell e Instrumental de administración de Windows (WMI) para configurar exámenes del Antivirus de Microsoft Defender. 

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
---|---
[Configuración y validación de exclusiones de archivos, carpetas y archivos abiertos por procesos en exámenes del Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md) | Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas de los exámenes a petición, los exámenes programados y la supervisión y el examen de protección en tiempo real siempre activados.
[Configurar opciones de análisis del Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Puede configurar antivirus de Microsoft Defender para incluir determinados tipos de archivos de almacenamiento de correo electrónico, puntos de copia de seguridad o de reanálisis y archivos archivados (como archivos .zip) en los exámenes. También puede habilitar el examen de archivos de red
[Configuración de la corrección de exámenes](configure-remediation-microsoft-defender-antivirus.md) | Configure lo que el Antivirus de Microsoft Defender debe hacer cuando detecte una amenaza y cuánto tiempo deben conservarse los archivos en cuarentena en la carpeta de cuarentena.
[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Configurar exámenes periódicos (programados), incluidos cuándo se deben ejecutar y si se ejecutan como exámenes completos o rápidos
[Configuración y ejecución de exámenes](run-scan-microsoft-defender-antivirus.md) | Ejecución y configuración de exámenes a petición mediante PowerShell, Instrumental de administración de Windows o individualmente en puntos de conexión con la aplicación Seguridad de Windows
[Revisión de los resultados del examen](review-scan-results-microsoft-defender-antivirus.md) | Revise los resultados de los exámenes mediante Configuration Manager de punto de conexión de Microsoft, Microsoft Intune o la aplicación Seguridad de Windows