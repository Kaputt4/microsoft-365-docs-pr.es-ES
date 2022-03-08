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
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 58ba49a49b41d80bacb31efa780530e44a146fc1
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326767"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Novedades de Microsoft Defender para Endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="1015880-30122012158800"></a>101.58.80 (30.122012.15880.0)

- La herramienta de línea de comandos ahora admite la restauración de archivos en cuarentena en una ubicación que no sea la que se detectó originalmente. Esto se puede hacer a través de `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- Correcciones de errores

## <a name="1015662-30121122156620"></a>101.56.62 (30.121122.15662.0)

- Se ha corregido un bloqueo de producto introducido en la 101.53.02 y que ha afectado a varios clientes

## <a name="1015302-30121112153020"></a>101.53.02 (30.121112.15302.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1015257-30121092152570"></a>101.52.57 (30.121092.15257.0)

- Se agregó una funcionalidad para detectar los jars de log4j vulnerables que usan Java aplicaciones. La máquina se inspecciona periódicamente para ejecutar procesos Java con tarros log4j cargados. La información se notifica al back-end de Microsoft Defender para endpoint y se expone en el área de administración de vulnerabilidades del portal.

## <a name="1014776-30121092147760"></a>101.47.76 (30.121092.14776.0)

- Se agregó un nuevo modificador a la herramienta de línea de comandos para controlar si los archivos se examinan durante los exámenes a petición. Esto se puede configurar a través de `mdatp config scan-archives --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
- Correcciones de errores

## <a name="1014513-30121082145130"></a>101.45.13 (30.121082.14513.0)

- A partir de esta versión, vamos a llevar la compatibilidad de Microsoft Defender para endpoint a las siguientes distros: 
  - Versiones RHEL6.7-6.10 y CentOS6.7-6.10.
  - Amazon Linux 2
  - Fedora 33 o posterior
- Correcciones de errores


## <a name="1014500-30121072145000"></a>101.45.00 (30.121072.14500.0)

- Se agregaron nuevos modificadores a la herramienta de línea de comandos:
  - Controlar el grado de paralelismo de los exámenes a petición. Esto se puede configurar a través de `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`. De forma predeterminada, se usa un grado de paralelismo `2` de.
  - Controlar si los exámenes después de las actualizaciones de inteligencia de seguridad están habilitados o deshabilitados. Esto se puede configurar a través de `mdatp config scan-after-definition-update --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
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

- EDR para Linux ya [está disponible por lo general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Se agregó un nuevo modificador de línea de comandos (`--ignore-exclusions`) para omitir las exclusiones av durante los exámenes personalizados (`mdatp scan custom`)
- Extendido `mdatp diagnostic create` con un nuevo parámetro (`--path [directory]`) que permite guardar los registros de diagnóstico en un directorio diferente
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

- Se agregó compatibilidad con los siguientes tipos de sistema de archivos: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`y `udf``vfat`
- Nueva sintaxis para la [herramienta de línea de comandos](linux-resources.md#configure-from-the-command-line).
- Mejoras de rendimiento & correcciones de errores

## <a name="1009070"></a>100.90.70

> [!WARNING]
> Al actualizar el paquete instalado desde una versión del producto anterior a 100.90.70, es posible que la actualización falle en las distribuciones basadas en Red Hat y SLES. Esto se debe a un cambio importante en una ruta de acceso de archivo. Una solución temporal es quitar el paquete anterior y, a continuación, instalar el más reciente. Este problema no existe en versiones más recientes.

- Las [exclusiones antivirus ahora admiten caracteres comodín](linux-exclusions.md#supported-exclusion-types)
- Se agregó la capacidad de solucionar [problemas de rendimiento a](linux-support-perf.md) través de la herramienta `mdatp` de línea de comandos
- Mejoras para que la instalación del paquete sea más sólida
- Mejoras de rendimiento & correcciones de errores
