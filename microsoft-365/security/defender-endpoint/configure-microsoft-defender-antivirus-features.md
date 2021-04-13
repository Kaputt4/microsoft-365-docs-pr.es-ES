---
title: Configurar características de Antivirus de Microsoft Defender
description: Puede configurar las características de Antivirus de Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, la directiva de grupo y PowerShell.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, configurar, configuración, Administrador de configuración, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, administración de dispositivos móviles, GP, directiva de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690818"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Configurar características de Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede configurar Antivirus de Microsoft Defender con varias herramientas, entre las que se incluyen:

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- Directiva de grupo
- Cmdlets de PowerShell
- Instrumental de administración de Windows (WMI)

Se pueden configurar las siguientes categorías generales de características:

- Protección entregada en la nube
- Protección siempre activa en tiempo real, incluida la protección basada en el comportamiento, heurística y de aprendizaje automático
- Cómo interactúan los usuarios finales con el cliente en puntos de conexión individuales

En los siguientes artículos se describe cómo realizar tareas clave al configurar Antivirus de Microsoft Defender. Cada artículo incluye instrucciones para la herramienta de configuración aplicable (o herramientas).

|Artículo  |Descripción  |
|---------|---------|
|[Usar la protección antivirus de Microsoft Defender proporcionada por la nube](cloud-protection-microsoft-defender-antivirus.md)     | Use la protección entregada en la nube para la detección avanzada, rápida y sólida de antivirus.        |
|[Configurar la protección de comportamiento, heurística y en tiempo real](configure-protection-features-microsoft-defender-antivirus.md)     |Habilite la protección antivirus basada en comportamiento, heurística y en tiempo real.         |
|[Configurar la interacción del usuario final con Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) | Configure cómo interactúan los usuarios finales de su organización con Antivirus de Microsoft Defender, qué notificaciones ven y si pueden invalidar la configuración. |

> [!TIP]
> También puede revisar el tema Temas de referencia para [herramientas](configuration-management-reference-microsoft-defender-antivirus.md) de administración y configuración para obtener información general sobre cada herramienta y vínculos para obtener más ayuda.