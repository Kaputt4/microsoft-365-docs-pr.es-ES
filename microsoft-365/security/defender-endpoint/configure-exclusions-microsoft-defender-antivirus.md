---
title: Configuración de exclusiones para exámenes de Antivirus de Microsoft Defender
description: Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas del análisis por Antivirus de Microsoft Defender. Valide las exclusiones con PowerShell.
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
ms.collection: m365-security-compliance
ms.openlocfilehash: c9796f4e5154fd46d1479f0cbfa25f2afaf4e9bb
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787520"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configuración y validación de exclusiones para exámenes de Antivirus de Microsoft Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de Antivirus de Microsoft Defender exámenes. Estas exclusiones se aplican a [los exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [a los exámenes a petición](run-scan-microsoft-defender-antivirus.md) y a la [protección y supervisión siempre en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md). Las exclusiones de los archivos abiertos por procesos solo se aplican a la protección en tiempo real.

## <a name="configure-and-validate-exclusions"></a>Configurar y validar exclusiones

Para configurar y validar exclusiones, consulte lo siguiente:

- [Configure y valide las exclusiones en función del nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Puede excluir archivos de Antivirus de Microsoft Defender exámenes en función de su extensión de archivo, nombre de archivo o ubicación.

- [Configure y valide las exclusiones de los archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Puede excluir archivos de los exámenes abiertos por un proceso específico.

## <a name="recommendations-for-defining-exclusions"></a>Recomendaciones para definir exclusiones

> [!IMPORTANT]
> Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos, como los que se usan en la administración empresarial, la administración de bases de datos y otros escenarios y situaciones empresariales.
>
> La definición de exclusiones reduce la protección ofrecida por Antivirus de Microsoft Defender. Siempre debe evaluar los riesgos asociados a la implementación de exclusiones y solo debe excluir los archivos que esté seguro de que no son malintencionados.

Tenga en cuenta los siguientes puntos al definir exclusiones:

- Las exclusiones son técnicamente una brecha de protección. Tenga en cuenta todas las opciones al definir exclusiones. Otras opciones pueden ser tan sencillas como asegurarse de que la ubicación excluida tenga las listas de control de acceso (ACL) adecuadas o establecer directivas en el modo de auditoría al principio.

- Revise las exclusiones periódicamente. Vuelva a comprobar y volver a aplicar las mitigaciones como parte del proceso de revisión.

- Idealmente, evite definir exclusiones en un esfuerzo por ser proactivo. Por ejemplo, no excluya algo solo porque cree que podría ser un problema en el futuro. Use exclusiones solo para problemas específicos, como los relacionados con el rendimiento o la compatibilidad de aplicaciones que las exclusiones podrían mitigar.

- Revise y audite los cambios en la lista de exclusiones. El equipo de seguridad debe conservar el contexto de por qué se agregó una exclusión determinada para evitar confusiones más adelante. El equipo de seguridad debe poder proporcionar respuestas específicas a preguntas sobre por qué existen exclusiones.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [exclusiones de Antivirus de Microsoft Defender en Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
