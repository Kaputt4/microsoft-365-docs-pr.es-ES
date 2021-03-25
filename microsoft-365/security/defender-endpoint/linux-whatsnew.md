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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198782"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="0e934-104">Novedades de Microsoft Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="0e934-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="0e934-105">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="0e934-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="0e934-106">Mejora del rendimiento para la situación en la que se agrega un punto de montaje completo a la lista de exclusión antivirus.</span><span class="sxs-lookup"><span data-stu-id="0e934-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="0e934-107">Antes de esta versión, el producto aún procesaba la actividad de archivo que se originó desde el punto de montaje.</span><span class="sxs-lookup"><span data-stu-id="0e934-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="0e934-108">A partir de esta versión, se suprime la actividad de archivo para puntos de montaje excluidos, lo que mejora el rendimiento del producto</span><span class="sxs-lookup"><span data-stu-id="0e934-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="0e934-109">Se agregó una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición.</span><span class="sxs-lookup"><span data-stu-id="0e934-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="0e934-110">Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="0e934-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="0e934-111">Otras mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="0e934-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="0e934-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="0e934-112">101.18.53</span></span>

- <span data-ttu-id="0e934-113">EDR para Linux ya está [disponible por lo general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="0e934-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="0e934-114">Se agregó un nuevo modificador de línea de comandos ( `--ignore-exclusions` ) para omitir las exclusiones av durante los exámenes personalizados ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="0e934-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="0e934-115">Extendido con un nuevo parámetro ( ) que permite guardar los registros de `mdatp diagnostic create` diagnóstico en un directorio `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="0e934-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="0e934-116">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="0e934-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="0e934-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="0e934-117">101.12.99</span></span>

- <span data-ttu-id="0e934-118">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="0e934-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="0e934-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="0e934-119">101.04.76</span></span>

- <span data-ttu-id="0e934-120">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="0e934-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="0e934-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="0e934-121">101.03.48</span></span>

- <span data-ttu-id="0e934-122">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="0e934-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="0e934-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="0e934-123">101.02.55</span></span>

- <span data-ttu-id="0e934-124">Se ha corregido un problema por el que el producto a veces no se inicia después de un reinicio o actualización</span><span class="sxs-lookup"><span data-stu-id="0e934-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="0e934-125">Se ha corregido un problema por el que la configuración de proxy no se conservaba en las actualizaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="0e934-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="0e934-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="0e934-126">101.00.75</span></span>

- <span data-ttu-id="0e934-127">Se agregó compatibilidad con los siguientes tipos de sistema de archivos: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` y `vfat`</span><span class="sxs-lookup"><span data-stu-id="0e934-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="0e934-128">Sintaxis nueva para la [herramienta de línea de comandos](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="0e934-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="0e934-129">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="0e934-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="0e934-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="0e934-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="0e934-131">Al actualizar el paquete instalado desde una versión del producto anterior a 100.90.70, es posible que la actualización falle en las distribuciones basadas en Red Hat y SLES.</span><span class="sxs-lookup"><span data-stu-id="0e934-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="0e934-132">Esto se debe a un cambio importante en una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="0e934-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="0e934-133">Una solución temporal es quitar el paquete anterior y, a continuación, instalar el más reciente.</span><span class="sxs-lookup"><span data-stu-id="0e934-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="0e934-134">Este problema no existe en versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="0e934-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="0e934-135">Las [exclusiones antivirus ahora admiten caracteres comodín](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="0e934-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="0e934-136">Se agregó la capacidad de solucionar [problemas de rendimiento a](linux-support-perf.md) través de la herramienta de línea de `mdatp` comandos</span><span class="sxs-lookup"><span data-stu-id="0e934-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="0e934-137">Mejoras para que la instalación del paquete sea más sólida</span><span class="sxs-lookup"><span data-stu-id="0e934-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="0e934-138">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="0e934-138">Performance improvements & bug fixes</span></span>
