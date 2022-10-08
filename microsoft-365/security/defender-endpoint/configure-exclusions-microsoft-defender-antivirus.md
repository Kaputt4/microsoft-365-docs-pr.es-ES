---
title: Configuración de exclusiones para exámenes Microsoft Defender Antivirus
description: Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas del examen por Microsoft Defender Antivirus. Valide las exclusiones con PowerShell.
keywords: ''
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.subservice: mde
ms.audience: ITPro
ms.topic: how-to
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 94addada13ca9b22a0d2b5bef6377dae175e7299
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319042"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configuración y validación de exclusiones para exámenes de antivirus de Microsoft Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de los exámenes Microsoft Defender Antivirus. Estas exclusiones se aplican a [los exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [a los exámenes a petición](run-scan-microsoft-defender-antivirus.md) y a la [protección y supervisión siempre en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md). Las exclusiones de los archivos abiertos por procesos solo se aplican a la protección en tiempo real.

## <a name="configure-and-validate-exclusions"></a>Configurar y validar exclusiones

Para configurar y validar exclusiones, consulte lo siguiente:

- [Configure y valide las exclusiones en función del nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Puede excluir archivos de los exámenes de Microsoft Defender Antivirus en función de su extensión de archivo, nombre de archivo o ubicación.

- [Configure y valide las exclusiones de los archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Puede excluir archivos de los exámenes abiertos por un proceso específico.

## <a name="recommendations-for-defining-exclusions"></a>Recomendaciones para definir exclusiones

> [!IMPORTANT]
> Microsoft Defender Antivirus incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos, como los que se usan en la administración empresarial, la administración de bases de datos y otros escenarios y situaciones empresariales.
>
> La definición de exclusiones reduce la protección que ofrece Microsoft Defender Antivirus. Siempre debe evaluar los riesgos asociados a la implementación de exclusiones y solo debe excluir los archivos que esté seguro de que no son malintencionados.

Tenga en cuenta los siguientes puntos al definir exclusiones:

- Las exclusiones son técnicamente una brecha de protección. Tenga en cuenta todas las opciones al definir exclusiones. Otras opciones pueden ser tan sencillas como asegurarse de que la ubicación excluida tenga las listas de control de acceso (ACL) adecuadas o establecer directivas en el modo de auditoría al principio.

- Revise las exclusiones periódicamente. Vuelva a comprobar y volver a aplicar las mitigaciones como parte del proceso de revisión.

- Idealmente, evite definir exclusiones en un esfuerzo por ser proactivo. Por ejemplo, no excluya algo solo porque cree que podría ser un problema en el futuro. Use exclusiones solo para problemas específicos, como los relacionados con el rendimiento o la compatibilidad de aplicaciones que las exclusiones podrían mitigar.

- Revise y audite los cambios en la lista de exclusiones. El equipo de seguridad debe conservar el contexto de por qué se agregó una exclusión determinada para evitar confusiones más adelante. El equipo de seguridad debe poder proporcionar respuestas específicas a preguntas sobre por qué existen exclusiones.

## <a name="audit-antivirus-exclusions"></a>Auditar exclusiones de antivirus

Exchange ha admitido la integración con la interfaz de examen antimalware (AMSI) desde la Novedades trimestral de junio de 2021 para Exchange. Se recomienda encarecidamente asegurarse de que estas actualizaciones están instaladas y AMSI funciona con las instrucciones proporcionadas por el equipo de Exchange, ya que esta integración permitirá la mejor capacidad para que Antivirus de Defender detecte y bloquee la explotación de Exchange.  

Muchas organizaciones excluyen los directorios de Exchange de los exámenes antivirus por motivos de rendimiento. Microsoft recomienda auditar las exclusiones de ANTIVIRUS en los sistemas exchange y evaluar si se pueden quitar sin afectar al rendimiento en su entorno para garantizar el nivel más alto de protección. Las exclusiones se pueden administrar mediante directiva de grupo, PowerShell o herramientas de administración de sistemas como Microsoft Endpoint Configuration Manager.

Para auditar las exclusiones de AV en un Exchange Server que ejecuta Antivirus de Defender, ejecute el comando **Get-MpPreference** desde un símbolo del sistema de PowerShell con privilegios elevados.

Si no se pueden quitar exclusiones para los procesos y carpetas de Exchange, la ejecución de un examen rápido en antivirus de Defender examinará los directorios y archivos de Exchange, independientemente de las exclusiones.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [exclusiones de antivirus de Microsoft Defender en Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
