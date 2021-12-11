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
ms.openlocfilehash: 74814304460c33b108b6216db853504f1956e59b
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168383"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Use Microsoft Endpoint Manager para configurar y administrar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

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
