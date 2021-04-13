---
title: Novedades de Microsoft Defender para Endpoint en Linux
description: Lista de cambios principales para ATP de Microsoft Defender en Linux.
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
ms.openlocfilehash: 2866cd0c9ee9b40aa9c08c4ff7dce64f745d3d03
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688638"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="6ffad-104">Novedades de Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="6ffad-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="6ffad-105">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="6ffad-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="6ffad-106">Microsoft Defender para Endpoint en Linux ya está disponible en versión preliminar para los clientes de Us Government.</span><span class="sxs-lookup"><span data-stu-id="6ffad-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="6ffad-107">Para obtener más información, vea [Microsoft Defender for Endpoint for US Government customers](gov.md).</span><span class="sxs-lookup"><span data-stu-id="6ffad-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="6ffad-108">Se ha corregido un problema por el que el uso de Microsoft Defender para Endpoint en Linux en sistemas con sistemas de archivos FUSE provocaba que el sistema operativo se colgara.</span><span class="sxs-lookup"><span data-stu-id="6ffad-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="6ffad-109">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="6ffad-110">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="6ffad-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="6ffad-111">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="6ffad-112">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="6ffad-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="6ffad-113">Mejora del rendimiento para la situación en la que se agrega un punto de montaje completo a la lista de exclusión antivirus.</span><span class="sxs-lookup"><span data-stu-id="6ffad-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="6ffad-114">Antes de esta versión, el producto aún procesaba la actividad de archivo que se originó desde el punto de montaje.</span><span class="sxs-lookup"><span data-stu-id="6ffad-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="6ffad-115">A partir de esta versión, se suprime la actividad de archivo para puntos de montaje excluidos, lo que mejora el rendimiento del producto</span><span class="sxs-lookup"><span data-stu-id="6ffad-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="6ffad-116">Se agregó una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición.</span><span class="sxs-lookup"><span data-stu-id="6ffad-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="6ffad-117">Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="6ffad-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="6ffad-118">Otras mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="6ffad-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="6ffad-119">101.18.53</span></span>

- <span data-ttu-id="6ffad-120">EDR para Linux ya está [disponible por lo general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="6ffad-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="6ffad-121">Se agregó un nuevo modificador de línea de comandos ( `--ignore-exclusions` ) para omitir las exclusiones av durante los exámenes personalizados ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="6ffad-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="6ffad-122">Extendido con un nuevo parámetro ( ) que permite guardar los registros de `mdatp diagnostic create` diagnóstico en un directorio `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="6ffad-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="6ffad-123">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="6ffad-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="6ffad-124">101.12.99</span></span>

- <span data-ttu-id="6ffad-125">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="6ffad-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="6ffad-126">101.04.76</span></span>

- <span data-ttu-id="6ffad-127">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="6ffad-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="6ffad-128">101.03.48</span></span>

- <span data-ttu-id="6ffad-129">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="6ffad-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="6ffad-130">101.02.55</span></span>

- <span data-ttu-id="6ffad-131">Se ha corregido un problema por el que el producto a veces no se inicia después de un reinicio o actualización</span><span class="sxs-lookup"><span data-stu-id="6ffad-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="6ffad-132">Se ha corregido un problema por el que la configuración de proxy no se conservaba en las actualizaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="6ffad-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="6ffad-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="6ffad-133">101.00.75</span></span>

- <span data-ttu-id="6ffad-134">Se agregó compatibilidad con los siguientes tipos de sistema de archivos: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` y `vfat`</span><span class="sxs-lookup"><span data-stu-id="6ffad-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="6ffad-135">Sintaxis nueva para la [herramienta de línea de comandos](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="6ffad-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="6ffad-136">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="6ffad-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="6ffad-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="6ffad-138">Al actualizar el paquete instalado desde una versión del producto anterior a 100.90.70, es posible que la actualización falle en las distribuciones basadas en Red Hat y SLES.</span><span class="sxs-lookup"><span data-stu-id="6ffad-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="6ffad-139">Esto se debe a un cambio importante en una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="6ffad-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="6ffad-140">Una solución temporal es quitar el paquete anterior y, a continuación, instalar el más reciente.</span><span class="sxs-lookup"><span data-stu-id="6ffad-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="6ffad-141">Este problema no existe en versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="6ffad-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="6ffad-142">Las [exclusiones antivirus ahora admiten caracteres comodín](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="6ffad-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="6ffad-143">Se agregó la capacidad de solucionar [problemas de rendimiento a](linux-support-perf.md) través de la herramienta de línea de `mdatp` comandos</span><span class="sxs-lookup"><span data-stu-id="6ffad-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="6ffad-144">Mejoras para que la instalación del paquete sea más sólida</span><span class="sxs-lookup"><span data-stu-id="6ffad-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="6ffad-145">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="6ffad-145">Performance improvements & bug fixes</span></span>
