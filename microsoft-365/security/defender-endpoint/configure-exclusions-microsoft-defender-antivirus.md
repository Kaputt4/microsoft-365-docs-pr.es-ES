---
title: Configurar exclusiones para exámenes de Antivirus de Microsoft Defender
description: Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas que microsoft Defender AV examina. Valide las exclusiones con PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 08f7f9d4a6e9e70d3ef071f30712b2ae53f4ea52
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764668"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configurar y validar exclusiones para exámenes de Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de los exámenes del Antivirus de Microsoft Defender. Estas exclusiones se aplican [a los exámenes programados,](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [](run-scan-microsoft-defender-antivirus.md)a los exámenes a petición y a la protección y supervisión siempre activas en tiempo [real.](configure-real-time-protection-microsoft-defender-antivirus.md) Las exclusiones de los archivos abiertos por proceso solo se aplican a la protección en tiempo real.

## <a name="configure-and-validate-exclusions"></a>Configurar y validar exclusiones

Para configurar y validar exclusiones, vea lo siguiente:

- [Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Esto le permite excluir archivos de exámenes de Antivirus de Microsoft Defender en función de su extensión de archivo, nombre de archivo o ubicación.

- [Configurar y validar exclusiones para los archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Esto permite excluir archivos de los exámenes abiertos por un proceso específico.

## <a name="recommendations-for-defining-exclusions"></a>Recomendaciones para definir exclusiones
[!IMPORTANT]
Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos, como los que se usan en la administración empresarial, la administración de bases de datos y otros escenarios y situaciones empresariales.  
La definición de exclusiones reduce la protección que ofrece Antivirus de Microsoft Defender. Siempre debe evaluar los riesgos asociados con la implementación de exclusiones y solo debe excluir los archivos que confía en que no son malintencionados.

A continuación se muestra una lista de recomendaciones que debe tener en cuenta al definir exclusiones:  

- Las exclusiones son técnicamente un vacío de protección: considere siempre mitigaciones adicionales al definir exclusiones. Las mitigaciones adicionales podrían ser tan sencillas como asegurarse de que la ubicación excluida tenga las listas de control de acceso (ACL) adecuadas, la directiva de auditoría, se procesa mediante un software actualizado, etc.

- Revise las exclusiones periódicamente. Vuelva a comprobar y volver a aplicar las mitigaciones como parte del proceso de revisión.

- Lo ideal es evitar definir exclusiones proactivas. Por ejemplo, no excluyas algo solo porque crees que podría ser un problema en el futuro. Use exclusiones solo para problemas específicos, principalmente en torno al rendimiento o, en ocasiones, a la compatibilidad de aplicaciones que las exclusiones podrían mitigar.

- Audite los cambios de la lista de exclusión. El administrador de seguridad debe conservar suficiente contexto en torno a por qué se agregó una exclusión determinada. Debería poder proporcionar una respuesta con un razonamiento específico sobre por qué se excluyó una determinada ruta de acceso.

## <a name="related-articles"></a>Artículos relacionados

- [Exclusiones de Antivirus de Microsoft Defender en Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes que se deben evitar al definir exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
