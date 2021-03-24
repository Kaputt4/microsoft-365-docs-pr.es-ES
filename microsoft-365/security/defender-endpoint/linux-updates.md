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
ms.openlocfilehash: adc19192764e8c57a20f14cc908be23e8d9bdbc8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070491"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a>Implementar actualizaciones para Microsoft Defender para endpoint para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.

> [!WARNING]
> Cada versión de Defender para Endpoint para Linux tiene una fecha de expiración, después de la cual ya no seguirá protegiendo el dispositivo. Debe actualizar el producto antes de esta fecha. Para comprobar la fecha de expiración, ejecute el siguiente comando:
> ```bash
> mdatp health --field product_expiration
> ```

Para actualizar Defender para Endpoint para Linux manualmente, ejecute uno de los siguientes comandos:

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
