---
title: Implementar actualizaciones de Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo implementar actualizaciones para Microsoft Defender para Endpoint en Linux en entornos empresariales.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, actualizaciones, implementación
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fe979da9c3f1144e595f31048689cbb6f6f4e959
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166859"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Implementar actualizaciones de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

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
