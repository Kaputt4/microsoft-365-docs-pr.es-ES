---
title: Implementar actualizaciones para ATP de Microsoft Defender para Linux
ms.reviewer: ''
description: Describe cómo implementar actualizaciones para ATP de Microsoft Defender para Linux en entornos empresariales.
keywords: microsoft, defender, atp, linux, actualizaciones, implementar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187726"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="0e85b-104">Implementar actualizaciones para Microsoft Defender para endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="0e85b-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0e85b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0e85b-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e85b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0e85b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e85b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e85b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0e85b-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0e85b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e85b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0e85b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0e85b-110">Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.</span><span class="sxs-lookup"><span data-stu-id="0e85b-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="0e85b-111">Cada versión de Defender para Endpoint para Linux tiene una fecha de expiración, después de la cual ya no seguirá protegiendo el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e85b-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="0e85b-112">Debe actualizar el producto antes de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="0e85b-112">You must update the product prior to this date.</span></span> <span data-ttu-id="0e85b-113">Para comprobar la fecha de expiración, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0e85b-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="0e85b-114">Para actualizar Defender para Endpoint para Linux manualmente, ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="0e85b-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="0e85b-115">RHEL y variantes (CentOS y Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="0e85b-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="0e85b-116">SLES y variantes</span><span class="sxs-lookup"><span data-stu-id="0e85b-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="0e85b-117">Sistemas Ubuntu y Debian</span><span class="sxs-lookup"><span data-stu-id="0e85b-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
