---
title: Ejecute y personalice exámenes programados y a petición.
description: Personalizar e iniciar exámenes Antivirus de Microsoft Defender en puntos de conexión en toda la red
keywords: análisis, programación, personalización, exclusiones, excluir archivos, corrección, resultados del examen, cuarentena, eliminación de amenazas, examen rápido, examen completo, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 63630c5a255e009a3fabaa0f2db168ded0e2c3c1
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490206"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Personalizar, iniciar y revisar los resultados de Antivirus de Microsoft Defender análisis y corrección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede usar la directiva de grupo, PowerShell y Windows Management Instrumentation (WMI) para configurar Antivirus de Microsoft Defender exámenes. 

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
---|---
[Configurar y validar exclusiones de archivos, carpetas y archivos abiertos por proceso en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md) | Puede excluir archivos (incluidos los archivos modificados por procesos especificados) y carpetas de exámenes a petición, exámenes programados y supervisión y análisis de protección siempre en tiempo real
[Configurar opciones de análisis del Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Puede configurar Antivirus de Microsoft Defender para incluir determinados tipos de archivos de almacenamiento de correo electrónico, puntos de copia de seguridad o reanúrlo, y archivos archivados (como .zip archivos) en los exámenes. También puede habilitar el examen de archivos de red
[Configurar la corrección para exámenes](configure-remediation-microsoft-defender-antivirus.md) | Configurar qué Antivirus de Microsoft Defender debe hacer cuando detecta una amenaza y cuánto tiempo deben conservarse los archivos en cuarentena en la carpeta de cuarentena
[Configurar exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
[Configurar y ejecutar exámenes](run-scan-microsoft-defender-antivirus.md) | Ejecutar y configurar exámenes a petición con PowerShell, Windows Management Instrumentation o individualmente en puntos de conexión con la Seguridad de Windows aplicación
[Revisar los resultados del examen](review-scan-results-microsoft-defender-antivirus.md) | Revisar los resultados de los exámenes mediante Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows examen