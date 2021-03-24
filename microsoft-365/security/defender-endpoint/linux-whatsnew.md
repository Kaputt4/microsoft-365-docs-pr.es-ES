---
title: Novedades de Microsoft Defender para Endpoint para Linux
description: Lista de cambios principales para ATP de Microsoft Defender para Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070488"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Novedades de Microsoft Defender para Endpoint para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a>101.18.53

- EDR para Linux ya está [disponible por lo general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
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
