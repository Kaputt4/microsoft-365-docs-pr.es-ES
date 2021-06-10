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
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Implementar actualizaciones de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.

> [!WARNING]
> Cada versión de Defender para Endpoint en Linux tiene una fecha de expiración, después de la cual ya no seguirá protegiendo el dispositivo. Debe actualizar el producto antes de esta fecha. Para comprobar la fecha de expiración, ejecute el siguiente comando:
> ```bash
> mdatp health --field product_expiration
> ```


Las funcionalidades de Microsoft Defender para endpoint disponibles generalmente son equivalentes, independientemente del canal de actualización usado para una implementación (Beta (Insider), Preview (Externa), Current (Production)).


Para actualizar Defender for Endpoint en Linux manualmente, ejecute uno de los siguientes comandos:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL y variantes (CentOS y Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES y variantes

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Sistemas Ubuntu y Debian

```bash
sudo apt-get install --only-upgrade mdatp
```
