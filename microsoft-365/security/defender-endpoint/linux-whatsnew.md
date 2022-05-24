---
title: Novedades de Microsoft Defender para punto de conexión en Linux
description: Lista de cambios principales para Microsoft Defender para punto de conexión en Linux.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, whatsnew, release
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: c58c447a4aed08af48576b461a638c1cd43aca83
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649251"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Novedades de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="1016880-30122042168800"></a>101.68.80 (30.122042.16880.0)

- Se ha agregado compatibilidad con la versión `2.6.32-754.47.1.el6.x86_64` del kernel cuando se ejecuta en RHEL 6.
- En RHEL 6, el producto ahora se puede instalar en dispositivos que ejecutan Unbreakable Enterprise Kernel (UEK)
- Se ha corregido un problema por el que el nombre del proceso a veces se mostraba incorrectamente como `unknown` cuando se ejecutaba `mdatp diagnostic real-time-protection-statistics`
- Se ha corregido un error por el que el producto a veces detectaba archivos incorrectamente dentro de la carpeta de cuarentena.
- Se ha corregido un problema por el que la `mdatp` herramienta de línea de comandos no funcionaba cuando `/opt` se montaba como un vínculo temporal.
- Mejoras de rendimiento & correcciones de errores

## <a name="1016577-30122032165770"></a>101.65.77 (30.122032.16577.0)

- Se ha mejorado el `conflicting_applications` campo en `mdatp health` para mostrar solo los 10 procesos más recientes y también para incluir los nombres de los procesos. Esto facilita la identificación de los procesos que pueden entrar en conflicto con Microsoft Defender para punto de conexión para Linux.
- Correcciones de errores

## <a name="1016274-30122022162740"></a>101.62.74 (30.122022.16274.0)

- Se ha corregido un problema por el que el producto bloqueaba incorrectamente el acceso a archivos de más de 2 GB al ejecutarse en versiones anteriores del kernel.
- Correcciones de errores

## <a name="1016093-30122012160930"></a>101.60.93 (30.122012.16093.0)

- Esta versión contiene una actualización de seguridad para [CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/)

## <a name="1016005-30122012160050"></a>101.60.05 (30.122012.16005.0)

- Se ha agregado compatibilidad con la versión 2.6.32-754.43.1.el6.x86_64 del kernel para RHEL 6.10
- Correcciones de errores

## <a name="1015880-30122012158800"></a>101.58.80 (30.122012.15880.0)

- La herramienta de línea de comandos ahora admite la restauración de archivos en cuarentena en una ubicación distinta a la en la que se detectó originalmente el archivo. Esto se puede hacer a través de `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- A partir de esta versión, la protección de red para Linux se puede evaluar a petición
- Correcciones de errores

## <a name="1015662-30121122156620"></a>101.56.62 (30.121122.15662.0)

- Se ha corregido un bloqueo de producto introducido en la versión 101.53.02 y que ha afectado a varios clientes.

## <a name="1015302-30121112153020"></a>101.53.02 (30.121112.15302.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1015257-30121092152570"></a>101.52.57 (30.121092.15257.0)

- Se ha agregado una funcionalidad para detectar los archivos JAR de log4j vulnerables que usan las aplicaciones Java. La máquina se inspecciona periódicamente para ejecutar procesos de Java con jars log4j cargados. La información se notifica al back-end Microsoft Defender para punto de conexión y se expone en el área Administración de vulnerabilidades del portal.

## <a name="1014776-30121092147760"></a>101.47.76 (30.121092.14776.0)

- Se ha agregado un nuevo modificador a la herramienta de línea de comandos para controlar si los archivos se examinan durante los exámenes a petición. Esto se puede configurar a través de `mdatp config scan-archives --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
- Correcciones de errores

## <a name="1014513-30121082145130"></a>101.45.13 (30.121082.14513.0)

- A partir de esta versión, se ofrece compatibilidad con Microsoft Defender para punto de conexión a las siguientes distribuciones: 
  - Versiones de RHEL6.7-6.10 y CentOS6.7-6.10.
  - Amazon Linux 2
  - Fedora 33 o superior
- Correcciones de errores


## <a name="1014500-30121072145000"></a>101.45.00 (30.121072.14500.0)

- Se han agregado nuevos modificadores a la herramienta de línea de comandos:
  - Control del grado de paralelismo para los exámenes a petición. Esto se puede configurar a través de `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`. De forma predeterminada, se usa un grado de paralelismo de `2` .
  - Controlar si los exámenes después de las actualizaciones de inteligencia de seguridad están habilitados o deshabilitados. Esto se puede configurar a través de `mdatp config scan-after-definition-update --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
- Cambiar el nivel de registro del producto ahora requiere elevación
- Correcciones de errores

## <a name="1013998-30121062139980"></a>101.39.98 (30.121062.13998.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1013427-30121052134270"></a>101.34.27 (30.121052.13427.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0)

- A partir de esta versión, las amenazas detectadas durante los exámenes antivirus a petición desencadenados a través del cliente de línea de comandos se corrigen automáticamente. Las amenazas detectadas durante los exámenes desencadenados a través de la interfaz de usuario todavía requieren una acción manual.
- `mdatp diagnostic real-time-protection-statistics` ahora admite dos conmutadores adicionales:
  - `--sort`: ordena la salida descendente por el número total de archivos examinados.
  - `--top N`: muestra los N resultados principales (solo funciona si `--sort` también se especifica)
- Mejoras de rendimiento & correcciones de errores

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Microsoft Defender para punto de conexión en Linux ya está disponible en versión preliminar para los clientes del Gobierno de EE. UU. Para obtener más información, consulte [Microsoft Defender para punto de conexión para clientes del gobierno de EE. UU](gov.md).
- Se ha corregido un problema por el que el uso de Microsoft Defender para punto de conexión en Linux en sistemas con sistemas de archivos FUSE provocaba que el sistema operativo se bloquease.
- Mejoras de rendimiento & otras correcciones de errores

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Mejora del rendimiento de la situación en la que se agrega un punto de montaje completo a la lista de exclusión del antivirus. Antes de esta versión, el producto seguía procesando la actividad de archivo que se originaba desde el punto de montaje. A partir de esta versión, se suprime la actividad de archivo de los puntos de montaje excluidos, lo que conduce a un mejor rendimiento del producto.
- Se ha agregado una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición. Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`
- Otras mejoras de rendimiento & correcciones de errores

## <a name="1011853"></a>101.18.53

- EDR para Linux ya está [disponible con carácter general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Se ha agregado un nuevo modificador de línea de comandos (`--ignore-exclusions`) para omitir las exclusiones de AV durante exámenes personalizados (`mdatp scan custom`)
- Extendido `mdatp diagnostic create` con un nuevo parámetro (`--path [directory]`) que permite guardar los registros de diagnóstico en un directorio diferente
- Mejoras de rendimiento & correcciones de errores

## <a name="1011299"></a>101.12.99

- Mejoras de rendimiento & correcciones de errores

## <a name="1010476"></a>101.04.76

- Correcciones de errores

## <a name="1010348"></a>101.03.48

- Correcciones de errores

## <a name="1010255"></a>101.02.55

- Se ha corregido un problema por el que el producto a veces no se iniciaba después de un reinicio o actualización.
- Se ha corregido un problema por el que la configuración del proxy no se conservaba en las actualizaciones del producto.

## <a name="1010075"></a>101.00.75

- Se ha agregado compatibilidad con los siguientes tipos de sistema de archivos: , , , , `nfs``jfs`, `overlay`, `ramfs`, `reiserfs``udf`y `fuseblk``fuse``ecryptfs``vfat`
- Nueva sintaxis para la [herramienta de línea de comandos](linux-resources.md#configure-from-the-command-line).
- Mejoras de rendimiento & correcciones de errores

## <a name="1009070"></a>100.90.70

> [!WARNING]
> Al actualizar el paquete instalado desde una versión de producto anterior a la 100.90.70, es posible que se produzca un error en las distribuciones basadas en Red Hat y SLES. Esto se debe a un cambio importante en una ruta de acceso de archivo. Una solución temporal consiste en quitar el paquete anterior y, a continuación, instalar el más reciente. Este problema no existe en las versiones más recientes.

- [Las exclusiones antivirus ahora admiten caracteres comodín](linux-exclusions.md#supported-exclusion-types)
- Se ha agregado la capacidad de [solucionar problemas de rendimiento](linux-support-perf.md) a través de la `mdatp` herramienta de línea de comandos.
- Mejoras para que la instalación del paquete sea más sólida
- Mejoras de rendimiento & correcciones de errores
