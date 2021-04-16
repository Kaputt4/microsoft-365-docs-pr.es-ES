---
title: Implementar actualizaciones para Microsoft Defender para endpoint para Linux
ms.reviewer: ''
description: Describe cómo implementar actualizaciones para Microsoft Defender para Endpoint para Linux en entornos empresariales.
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
ms.openlocfilehash: 77b428e359596e73e08dc04f15190ecf68db29be
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861152"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="2f443-104">Implementar actualizaciones para Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="2f443-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2f443-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2f443-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f443-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2f443-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f443-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f443-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2f443-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2f443-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f443-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2f443-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2f443-110">Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.</span><span class="sxs-lookup"><span data-stu-id="2f443-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="2f443-111">Cada versión de Defender para Endpoint para Linux tiene una fecha de expiración, después de la cual ya no seguirá protegiendo el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f443-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="2f443-112">Debe actualizar el producto antes de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="2f443-112">You must update the product prior to this date.</span></span> <span data-ttu-id="2f443-113">Para comprobar la fecha de expiración, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2f443-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="2f443-114">Para actualizar Defender para Endpoint para Linux manualmente, ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="2f443-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="2f443-115">RHEL y variantes (CentOS y Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="2f443-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="2f443-116">SLES y variantes</span><span class="sxs-lookup"><span data-stu-id="2f443-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="2f443-117">Sistemas Ubuntu y Debian</span><span class="sxs-lookup"><span data-stu-id="2f443-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
