---
title: Configurar exclusiones para Antivirus de Microsoft Defender exámenes
description: Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas de que Antivirus de Microsoft Defender. Valide las exclusiones con PowerShell.
keywords: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 6ea89e3e062cfa0ab5a4bd684fed309a041db769
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168287"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configurar y validar exclusiones para Antivirus de Microsoft Defender exámenes

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


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

- Las exclusiones son técnicamente un vacío de protección. Tenga en cuenta todas las opciones al definir exclusiones. Otras opciones pueden ser tan sencillas como asegurarse de que la ubicación excluida tenga las listas de control de acceso (ACL) adecuadas o establecer directivas en el modo de auditoría al principio.

- Revise las exclusiones periódicamente. Vuelva a comprobar y volver a aplicar mitigaciones como parte del proceso de revisión.

- Lo ideal es evitar definir exclusiones en un esfuerzo por ser proactivo. Por ejemplo, no excluyas algo solo porque crees que podría ser un problema en el futuro. Use exclusiones solo para problemas específicos, como los relacionados con el rendimiento o la compatibilidad de aplicaciones que las exclusiones podrían mitigar.

- Revise y audite los cambios en la lista de exclusiones. El equipo de seguridad debe conservar el contexto en torno a por qué se agregó una exclusión determinada para evitar confusiones más adelante. El equipo de seguridad debe poder proporcionar respuestas específicas a preguntas sobre por qué existen exclusiones.

## <a name="see-also"></a>Recursos adicionales

- [Antivirus de Microsoft Defender exclusiones en Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
