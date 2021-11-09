---
title: Configurar Antivirus de Microsoft Defender con Microsoft Endpoint Manager
description: Use Microsoft Endpoint Manager y Microsoft Intune para configurar Antivirus de Microsoft Defender y Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: eed1b0d19efe21d4bb1ba81dfb36964c6d80894c
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881722"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Use Microsoft Endpoint Manager para configurar y administrar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para configurar los Antivirus de Microsoft Defender digitalizaciones. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Configuration Manager](/mem/configmgr/core/understand/introduction) ahora forman parte de Endpoint Manager.

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Configurar Antivirus de Microsoft Defender exámenes en Endpoint Manager

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Vaya a **Endpoint Security**.

3. En **Administrar**, elija **Antivirus**.

4. Seleccione la directiva Antivirus de Microsoft Defender usuario.

5. En **Administrar**, elija **Propiedades**.

6. Junto a **Opciones de configuración**, elija **Editar**.

7. Expanda la **sección** Examinar y revise o edite la configuración del examen.

8. Elija **Revisar y guardar**

> [!TIP]
> ¿Necesita ayuda? Consulte [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).

## <a name="related-articles"></a>Artículos relacionados

- [Artículos de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
