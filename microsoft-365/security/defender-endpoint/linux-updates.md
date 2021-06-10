---
title: Implementar actualizaciones de Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo implementar actualizaciones para Microsoft Defender para Endpoint en Linux en entornos empresariales.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, actualizaciones, implementación
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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274729"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="60aaa-104">Implementar actualizaciones de Microsoft Defender para punto de conexión en Linux</span><span class="sxs-lookup"><span data-stu-id="60aaa-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="60aaa-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="60aaa-105">**Applies to:**</span></span>
- [<span data-ttu-id="60aaa-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="60aaa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="60aaa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60aaa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="60aaa-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="60aaa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="60aaa-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="60aaa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="60aaa-110">Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.</span><span class="sxs-lookup"><span data-stu-id="60aaa-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="60aaa-111">Cada versión de Defender para Endpoint en Linux tiene una fecha de expiración, después de la cual ya no seguirá protegiendo el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60aaa-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="60aaa-112">Debe actualizar el producto antes de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="60aaa-112">You must update the product prior to this date.</span></span> <span data-ttu-id="60aaa-113">Para comprobar la fecha de expiración, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="60aaa-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="60aaa-114">Las funcionalidades de Microsoft Defender para endpoint disponibles generalmente son equivalentes, independientemente del canal de actualización usado para una implementación (Beta (Insider), Preview (Externa), Current (Production)).</span><span class="sxs-lookup"><span data-stu-id="60aaa-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="60aaa-115">Para actualizar Defender for Endpoint en Linux manualmente, ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="60aaa-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="60aaa-116">RHEL y variantes (CentOS y Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="60aaa-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="60aaa-117">SLES y variantes</span><span class="sxs-lookup"><span data-stu-id="60aaa-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="60aaa-118">Sistemas Ubuntu y Debian</span><span class="sxs-lookup"><span data-stu-id="60aaa-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
