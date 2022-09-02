---
title: Implementar actualizaciones de Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo implementar actualizaciones para Microsoft Defender para punto de conexión en Linux en entornos empresariales.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, actualizaciones, implementar
ms.service: microsoft-365-security
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
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 9987c5b6921d39bc5f3c0550388bddbfc5c91a92
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521669"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Implementar actualizaciones de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.

> [!WARNING]
> Cada versión de Defender para punto de conexión en Linux tiene una fecha de expiración, después de la cual ya no seguirá protegiendo el dispositivo. Debe actualizar el producto antes de esta fecha. Para comprobar la fecha de expiración, ejecute el siguiente comando:
> ```bash
> mdatp health --field product_expiration
> ```


Las funcionalidades de Microsoft Defender para punto de conexión disponibles con carácter general son equivalentes independientemente del canal de actualización usado para una implementación (Beta (Insider), Versión preliminar (externo), Actual (producción)).


Para actualizar Defender para punto de conexión manualmente en Linux, ejecute uno de los siguientes comandos:

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

> [!IMPORTANT]
> Al integrar Microsoft Defender para punto de conexión y Defender for Cloud, el agente mdatp recibirá automáticamente las actualizaciones de forma predeterminada.
