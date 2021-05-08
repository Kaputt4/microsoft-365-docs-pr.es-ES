---
title: Configurar exclusiones para Antivirus de Microsoft Defender exámenes
description: Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas de que Antivirus de Microsoft Defender. Valide las exclusiones con PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275125"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configurar y validar exclusiones para Antivirus de Microsoft Defender exámenes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de Antivirus de Microsoft Defender análisis. Estas exclusiones se aplican [a los exámenes programados,](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [](run-scan-microsoft-defender-antivirus.md)a los exámenes a petición y a la protección y supervisión siempre activas en tiempo [real.](configure-real-time-protection-microsoft-defender-antivirus.md) Las exclusiones de los archivos abiertos por proceso solo se aplican a la protección en tiempo real.

## <a name="configure-and-validate-exclusions"></a>Configurar y validar exclusiones

Para configurar y validar exclusiones, vea lo siguiente:

- [Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Puede excluir archivos de los Antivirus de Microsoft Defender en función de su extensión de archivo, nombre de archivo o ubicación.

- [Configurar y validar exclusiones para los archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Puede excluir archivos de los exámenes abiertos por un proceso específico.

## <a name="recommendations-for-defining-exclusions"></a>Recomendaciones para definir exclusiones

> [!IMPORTANT]
> Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos, como los que se usan en la administración empresarial, la administración de bases de datos y otros escenarios y situaciones empresariales.  
> 
> La definición de exclusiones reduce la protección que ofrece Antivirus de Microsoft Defender. Siempre debe evaluar los riesgos asociados con la implementación de exclusiones y solo debe excluir los archivos que confía en que no son malintencionados.

Tenga en cuenta los siguientes puntos al definir exclusiones:  

- Las exclusiones son técnicamente un vacío de protección. Tenga en cuenta siempre las mitigaciones al definir exclusiones. Otras mitigaciones podrían ser tan sencillas como asegurarse de que la ubicación excluida tenga las listas de control de acceso (ACL) adecuadas, la directiva de auditoría, se procesa mediante un software actualizado, etc.

- Revise las exclusiones periódicamente. Vuelva a comprobar y volver a aplicar las mitigaciones como parte del proceso de revisión.

- Lo ideal es evitar definir exclusiones que pretenda ser proactivas. Por ejemplo, no excluyas algo solo porque crees que podría ser un problema en el futuro. Use exclusiones solo para problemas específicos, como los relacionados con el rendimiento o la compatibilidad de aplicaciones que las exclusiones podrían mitigar.

- Audite los cambios de la lista de exclusión. El administrador de seguridad debe conservar suficiente contexto en torno a por qué se agregó una exclusión determinada. Debería poder proporcionar una respuesta con un razonamiento específico sobre por qué se excluyó una determinada ruta de acceso.

## <a name="related-articles"></a>Artículos relacionados

- [Antivirus de Microsoft Defender exclusiones en Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
