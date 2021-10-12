---
title: Novedades de Microsoft Defender para Endpoint en Linux
description: Lista de cambios principales para Microsoft Defender para Endpoint en Linux.
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, whatsnew, release
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
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 1692c80d400cbae3ebaefd2a6995cba9c362c580
ms.sourcegitcommit: df1ad7118c4a95a310a4f17124322a6ae6ace26f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "60268901"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Novedades de Microsoft Defender para Endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1014500-30121072145000"></a>101.45.00 (30.121072.14500.0)

- Se agregaron nuevos modificadores a la herramienta de línea de comandos:
  - Controlar el grado de paralelismo de los exámenes a petición. Esto se puede configurar a través `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]` de . De forma predeterminada, se usa un grado de paralelismo `2` de.
  - Controlar si los exámenes después de las actualizaciones de inteligencia de seguridad están habilitados o deshabilitados. Esto se puede configurar a través `mdatp config scan-after-definition-update --value [enabled/disabled]` de . De forma predeterminada, se establece en `enabled` .
  - Controlar si los archivos se examinan durante los exámenes a petición. Esto se puede configurar a través `mdatp config scan-archives --value [enabled/disabled]` de . De forma predeterminada, se establece en `enabled` .
- Cambiar el nivel de registro de producto ahora requiere elevación
- Correcciones de errores

## <a name="1013998-30121062139980"></a>101.39.98 (30.121062.13998.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1013427-30121052134270"></a>101.34.27 (30.121052.13427.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0)

- A partir de esta versión, las amenazas detectadas durante los exámenes antivirus a petición desencadenados a través del cliente de línea de comandos se corrigen automáticamente. Las amenazas detectadas durante los exámenes desencadenados a través de la interfaz de usuario aún requieren una acción manual.
- `mdatp diagnostic real-time-protection-statistics` ahora admite dos modificadores adicionales:
  - `--sort`: ordena el resultado descendente por número total de archivos analizados
  - `--top N`: muestra los resultados N superiores (solo funciona si `--sort` también se especifica)
- Mejoras de rendimiento & correcciones de errores

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Microsoft Defender para Endpoint en Linux ya está disponible en versión preliminar para los clientes de Us Government. Para obtener más información, vea [Microsoft Defender for Endpoint for US Government customers](gov.md).
- Se ha corregido un problema por el que el uso de Microsoft Defender para Endpoint en Linux en sistemas con sistemas de archivos FUSE provocaba que el sistema operativo se colgara.
- Mejoras de rendimiento & correcciones de errores

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Mejora del rendimiento para la situación en la que se agrega un punto de montaje completo a la lista de exclusión antivirus. Antes de esta versión, el producto aún procesaba la actividad de archivo que se originó desde el punto de montaje. A partir de esta versión, se suprime la actividad de archivo para puntos de montaje excluidos, lo que mejora el rendimiento del producto
- Se agregó una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición. Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`
- Otras mejoras de rendimiento & correcciones de errores

## <a name="1011853"></a>101.18.53

- EDR para Linux ya [está disponible en general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Se agregó un nuevo modificador de línea de comandos ( `--ignore-exclusions` ) para omitir las exclusiones av durante los exámenes personalizados ( `mdatp scan custom` )
- Extendido con un nuevo parámetro ( ) que permite guardar los registros de `mdatp diagnostic create` diagnóstico en un directorio `--path [directory]` diferente
- Mejoras de rendimiento & correcciones de errores

## <a name="1011299"></a>101.12.99

- Mejoras de rendimiento & correcciones de errores

## <a name="1010476"></a>101.04.76

- Correcciones de errores

## <a name="1010348"></a>101.03.48

- Correcciones de errores

## <a name="1010255"></a>101.02.55

- Se ha corregido un problema por el que el producto a veces no se inicia después de un reinicio o actualización
- Se ha corregido un problema por el que la configuración de proxy no se conservaba en las actualizaciones de productos.

## <a name="1010075"></a>101.00.75

- Se agregó compatibilidad con los siguientes tipos de sistema de archivos: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` y `vfat`
- Sintaxis nueva para la [herramienta de línea de comandos](linux-resources.md#configure-from-the-command-line).
- Mejoras de rendimiento & correcciones de errores

## <a name="1009070"></a>100.90.70

> [!WARNING]
> Al actualizar el paquete instalado desde una versión del producto anterior a 100.90.70, es posible que la actualización falle en las distribuciones basadas en Red Hat y SLES. Esto se debe a un cambio importante en una ruta de acceso de archivo. Una solución temporal es quitar el paquete anterior y, a continuación, instalar el más reciente. Este problema no existe en versiones más recientes.

- Las [exclusiones antivirus ahora admiten caracteres comodín](linux-exclusions.md#supported-exclusion-types)
- Se agregó la capacidad de solucionar [problemas de rendimiento a](linux-support-perf.md) través de la herramienta de línea de `mdatp` comandos
- Mejoras para que la instalación del paquete sea más sólida
- Mejoras de rendimiento & correcciones de errores
