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
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="21b1f-104">Novedades de Microsoft Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="21b1f-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="21b1f-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="21b1f-105">101.18.53</span></span>

- <span data-ttu-id="21b1f-106">EDR para Linux ya está [disponible por lo general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="21b1f-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="21b1f-107">Se agregó un nuevo modificador de línea de comandos ( `--ignore-exclusions` ) para omitir las exclusiones av durante los exámenes personalizados ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="21b1f-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="21b1f-108">Extendido con un nuevo parámetro ( ) que permite guardar los registros de `mdatp diagnostic create` diagnóstico en un directorio `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="21b1f-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="21b1f-109">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="21b1f-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="21b1f-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="21b1f-110">101.12.99</span></span>

- <span data-ttu-id="21b1f-111">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="21b1f-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="21b1f-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="21b1f-112">101.04.76</span></span>

- <span data-ttu-id="21b1f-113">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="21b1f-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="21b1f-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="21b1f-114">101.03.48</span></span>

- <span data-ttu-id="21b1f-115">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="21b1f-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="21b1f-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="21b1f-116">101.02.55</span></span>

- <span data-ttu-id="21b1f-117">Se ha corregido un problema por el que el producto a veces no se inicia después de un reinicio o actualización</span><span class="sxs-lookup"><span data-stu-id="21b1f-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="21b1f-118">Se ha corregido un problema por el que la configuración de proxy no se conservaba en las actualizaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="21b1f-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="21b1f-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="21b1f-119">101.00.75</span></span>

- <span data-ttu-id="21b1f-120">Se agregó compatibilidad con los siguientes tipos de sistema de archivos: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` y `vfat`</span><span class="sxs-lookup"><span data-stu-id="21b1f-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="21b1f-121">Sintaxis nueva para la [herramienta de línea de comandos](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="21b1f-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="21b1f-122">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="21b1f-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="21b1f-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="21b1f-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="21b1f-124">Al actualizar el paquete instalado desde una versión del producto anterior a 100.90.70, es posible que la actualización falle en las distribuciones basadas en Red Hat y SLES.</span><span class="sxs-lookup"><span data-stu-id="21b1f-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="21b1f-125">Esto se debe a un cambio importante en una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="21b1f-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="21b1f-126">Una solución temporal es quitar el paquete anterior y, a continuación, instalar el más reciente.</span><span class="sxs-lookup"><span data-stu-id="21b1f-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="21b1f-127">Este problema no existe en versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="21b1f-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="21b1f-128">Las [exclusiones antivirus ahora admiten caracteres comodín](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="21b1f-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="21b1f-129">Se agregó la capacidad de solucionar [problemas de rendimiento a](linux-support-perf.md) través de la herramienta de línea de `mdatp` comandos</span><span class="sxs-lookup"><span data-stu-id="21b1f-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="21b1f-130">Mejoras para que la instalación del paquete sea más sólida</span><span class="sxs-lookup"><span data-stu-id="21b1f-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="21b1f-131">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="21b1f-131">Performance improvements & bug fixes</span></span>
