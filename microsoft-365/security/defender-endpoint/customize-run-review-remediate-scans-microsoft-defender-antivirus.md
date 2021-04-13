---
title: Ejecutar y personalizar exámenes programados y a petición
description: Personalice e inicie exámenes de Antivirus de Microsoft Defender en puntos de conexión en toda la red.
keywords: análisis, programación, personalización, exclusiones, excluir archivos, corrección, resultados del examen, cuarentena, eliminación de amenazas, examen rápido, examen completo, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 8aa735cf7490a451a5758c3799bd08dff61f8063
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690798"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Personalizar, iniciar y revisar los resultados de los exámenes y la corrección del Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puedes usar la directiva de grupo, PowerShell e Instrumental de administración de Windows (WMI) para configurar exámenes del Antivirus de Microsoft Defender. 

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
---|---
[Configurar y validar exclusiones de archivos, carpetas y procesos abiertos en exámenes del Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md) | Puede excluir archivos (incluidos los archivos modificados por procesos especificados) y carpetas de exámenes a petición, exámenes programados y supervisión y análisis de protección siempre en tiempo real
[Configurar opciones de análisis de Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Puede configurar Antivirus de Microsoft Defender para incluir determinados tipos de archivos de almacenamiento de correo electrónico, puntos de copia de seguridad o reanúdes, y archivos archivados (como archivos .zip) en los exámenes. También puede habilitar el examen de archivos de red
[Configurar la corrección para exámenes](configure-remediation-microsoft-defender-antivirus.md) | Configurar lo que antivirus de Microsoft Defender debe hacer cuando detecte una amenaza y cuánto tiempo deben conservarse los archivos en cuarentena en la carpeta de cuarentena
[Configurar exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
[Configurar y ejecutar exámenes](run-scan-microsoft-defender-antivirus.md) | Ejecutar y configurar exámenes a petición con PowerShell, Instrumental de administración de Windows o individualmente en puntos de conexión con la aplicación Seguridad de Windows
[Revisar los resultados del examen](review-scan-results-microsoft-defender-antivirus.md) | Revisar los resultados de los exámenes con Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows